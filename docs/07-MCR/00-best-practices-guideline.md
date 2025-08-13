## Plan for LLMs to Write MCR Files (REST API Documentation) Following Best Practices

When generating MCR files for REST APIs, always adhere to the following principles:

1. **Consistent Field Format**
   - Use camelCase for all field names (e.g., userId, orderDate).
   - Avoid snake_case, PascalCase, or other formats.

2. **Endpoint Naming**
   - Use plural nouns for resource endpoints (e.g., /users, /orders).
   - Endpoints should be resource-focused and descriptive.
   - Avoid verbs in endpoint paths (use HTTP methods to indicate actions).

3. **Nested Endpoints**
   - When nesting, always include the parent object as a path parameter (e.g., /users/{userId}/orders).
   - In nested responses, include only the relevant fields from the parent object to keep payloads simple and focused.

4. **HTTP Methods**
   - Use standard HTTP methods: GET (retrieve), POST (create), PUT/PATCH (update), DELETE (remove).
   - DELETE operations should return HTTP 204 No Content on success.
   - Avoid using non-standard or custom methods.

5. **Request/Response Consistency**
   - Clearly document all required and optional fields.
   - Use consistent response structures:
     - **List responses** should return an object with a `data` array and a `pagination` object (see below).
     - **Item responses** should return an object with a `data` field containing the resource.
   - Include standard error formats with clear messages and codes.

6. **Pagination Schema**
   - Use a standard pagination object in list responses:
     ```json
     {
       "data": [ ... ],
       "pagination": {
         "page": 1,
         "pageSize": 20,
         "total": 100,
         "totalPages": 5
       }
     }
     ```
   - Document all pagination parameters (e.g., `page`, `pageSize`).

7. **Status Codes**
   - Use standard HTTP status codes (200, 201, 204, 400, 404, 409, 500, etc.).
   - Document the expected status code for each endpoint and scenario.

8. **Filtering, Sorting, Pagination**
   - Support filtering, sorting, and pagination via query parameters where appropriate.
   - Document all supported parameters and their formats.

9. **Examples**
   - Provide example requests and responses for each endpoint.
   - Use realistic data and show both success and error cases.

10. **Authentication & Authorization**
    - Document authentication requirements (e.g., Bearer token).
    - Specify which endpoints require authentication and what permissions are needed.

11. **Versioning**
    - Indicate the API version in the path or header (e.g., /v1/users).
    - Document versioning strategy.

12. **Other Guidelines**
    - Do not use HATEOAS for now.
    - Prefer clear and minimal schemas.
    - Use ISO 8601 for date/time fields.
    - Use UUIDs for resource identifiers unless otherwise specified.
    - Document all enums and allowed values.
    - Always provide error examples.

## DRF-Style Schema Patterns

When documenting or designing REST APIs, follow these Django Rest Framework (DRF) inspired schema conventions:

### 1. List (Collection) Response
A paginated list response should have:
- `results`: the array of objects
- `count`: total number of objects matching the query
- `next`: URL to the next page, or null
- `previous`: URL to the previous page, or null

Example:
```json
{
  "count": 123,
  "next": "https://api.example.com/v1/items/?page=3",
  "previous": "https://api.example.com/v1/items/?page=1",
  "results": [
    { /* item object */ },
    { /* item object */ }
  ]
}
```

### 2. Single Item Response
A single resource is returned as an object, not wrapped:
```json
{
  "id": "abc123",
  "name": "Item Name",
  "createdAt": "2025-07-28T13:00:00Z"
  // ...other fields
}
```

### 3. Error Response
Standardized error responses:
```json
{
  "detail": "Error message here.",
  "code": "error_code"
}
```
Or for field validation errors:
```json
{
  "field_name": ["Error message for this field."]
}
```

### 4. DELETE Response
- On success, return HTTP 204 No Content with an empty body.

### 5. Filtering, Sorting, and Pagination
- Pagination via query parameters: `?page=2&page_size=20`
- Filtering and ordering via query parameters: `?ordering=name` or `?search=abc`
- Document all supported filters and ordering fields.

### 6. Other Patterns
- Use ISO 8601 for all date/time fields.
- Use UUIDs for resource IDs where possible.
- Do not use HATEOAS for now.
- Plural, resource-focused endpoints.