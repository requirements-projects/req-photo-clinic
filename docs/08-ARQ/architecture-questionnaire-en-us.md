# Architecture Requirements Questionnaire

## 1. Architectural Documentation Introduction

1. What is the main objective of the system being developed?
2. Who are the main stakeholders and their expectations for the system?
3. What are the main technical and business challenges that the architecture must solve?
4. What is the expected development timeline and system lifespan?
5. Are there any legacy systems that need to be integrated? If yes, which ones?
6. What are the most important quality attributes for the system? (scalability, availability, security, usability, etc.)
7. What are the main technical, budgetary, or time constraints of the project?

## 2. Application Types

8. Which platforms should the system support? (web, mobile, desktop)
9. For web applications:
   - Does the system need to work offline?
   - Which browsers and versions need to be supported?
   - Are there any specific SEO or performance requirements?

10. For mobile applications:
    - Which platforms should be supported? (iOS, Android)
    - Will the application be native, hybrid, or cross-platform?
    - What device-specific features are required? (camera, GPS, notifications)

11. For desktop applications:
    - Which operating systems need to be supported?
    - Does the application need to work offline?
    - Are there any hardware integration requirements?

12. What is the profile of end users in terms of:
    - Technical knowledge
    - Frequency of use
    - Usage context (corporate, consumer, field)
    - Accessibility requirements

13. Are there internationalization and localization requirements?

## 3. Cloud-Agnostic Infrastructure Foundation

14. Are there any preferences or restrictions regarding cloud providers?
15. Will the system need to run on multiple cloud providers simultaneously?
16. Are there any requirements for on-premises or hybrid deployment?
17. What compliance and regulatory requirements need to be considered? (GDPR, CCPA, etc.)
18. What is the expected data volume and traffic:
    - At launch
    - After 1 year
    - During peak usage
19. Are there any specific latency or response time requirements?
20. What is the backup, disaster recovery, and business continuity strategy?
21. Are there any specific requirements for the geographical location of data?
22. If you had to choose a cloud service, which would be most appropriate? (e.g., AWS, Google Cloud, Azure, etc.)

## 4. Deployment Strategy and Continuous Delivery

23. What is the expected release frequency for the system?
24. Are there maintenance windows or deployment restrictions?
25. What is the acceptable level of downtime during updates?
26. How should the QA and approval process be integrated into the delivery pipeline?
27. What environments are needed? (development, test, staging, production)
28. Are there specific requirements for version rollback?
29. What metrics are critical for system monitoring?
30. Which stakeholders need to be notified during the deployment process?
31. Are there any specific requirements for feature flags or gradual rollouts?

## 5. Domain Analysis

32. What are the main business processes the system needs to support?
33. Who are the domain experts who can validate the business model?
34. Are there specific business domain terms that should be standardized?
35. How do business processes relate to each other?
36. What are the critical business rules that must be preserved in any implementation?
37. Are there workflows or processes that involve external actors?
38. What are the main business entities and their lifecycles?
39. What are the significant events in the domain that could trigger processes?
40. Which domains are considered "core" to the business's competitive advantage?

## 6. Application Architecture

41. What are the main use cases of the system?
42. What are the performance requirements for each critical use case?
43. Are there operations that should be processed in batch or real-time?
44. How should the system behave in case of external component failures?
45. What integrations with external systems are needed?
46. What authentication and authorization patterns should be implemented?
47. Are there specific requirements for auditing system actions?
48. What are the expected volumes for:
    - Concurrent users
    - Transactions per second
    - Data volume per period
49. Are there specific caching or optimization requirements?

## 7. Implementation and Evolution

50. What technologies is the development team experienced with?
51. Are there any preferences or restrictions regarding programming languages?
52. How will technical documentation be managed?
53. What code quality practices will be adopted? (code review, automated testing)
54. How will technical debt be measured in the project?
55. What is the strategy for evolving the data schema?
56. How will data migrations be handled during updates?
57. Is there any requirement for backward compatibility with previous API versions?
58. What is the strategy for deprecating obsolete features?
59. How will the team's technical knowledge about the architecture be managed?

## Additional Information

60. Are there any benchmarks or reference systems that should be considered?
61. What are the main technical risks identified so far?
62. Are there any architectural decisions that have already been made and should be respected?
63. What is the available budget for infrastructure and tools?
64. What business metrics will be used to evaluate the system's success?
