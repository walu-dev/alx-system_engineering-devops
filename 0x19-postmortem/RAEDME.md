Postmortem: Outage on Web Application

Issue Summary: During from August 10, 2023 12:00 PM to August 11, 2023 1:00 PM(EAT): The web application experienced intermittent downtime resulting in slow response time and partial service disruption. Approximately 25% of users were affected in this period.

Timeline:

August 10, 2023 12:00 PM to August 11, 2023 1:00 PM(EAT): The issue was detected when monitoring alerts indicated a significant increase in response time.

The engineering team immediately started an investigation, suspecting a potential database problem.

The incident was escalated to the database administration team to assess the potential impact of the schema changes on the cluster’s performance.

Further investigation revealed no abnormalities within the database cluster, prompting the team to explore other areas of the system.

August 11, 2023 1:00 PM(EAT): The root cause was identified as an overloaded cache layer, leading to increased latency and intermittent failures.

Root Cause and Resolution: The root cause of the issue was an overloaded cache layer. The increased load on the system caused the cache to evict frequently accessed data, resulting in higher latency and intermittent failures. The cache’s eviction policy was not adequately configured to handle the sudden surge in traffic.

To resolve the issue, the infrastructure team adjusted the cache configuration by increasing its capacity and optimizing the eviction policy. This measure aimed to prevent similar cache overload situations in the future.

Corrective and Preventative Measures:

Optimize cache eviction policies: Review and fine-tune the cache eviction policies based on usage patterns and anticipated traffic fluctuations.
Scale cache infrastructure: Evaluate the current cache infrastructure and determine if additional resources are required to handle peak loads.
Tasks to address the issue:

Patch cache eviction policies: Adjust the cache eviction policies to prioritize frequently accessed data while considering memory constraints.
Evaluate cache infrastructure: Assess the current cache infrastructure’s capacity and explore options for scaling or introducing distributed caching.

The following preventative measures aim to enhance the reliability and performance of our web application to prevent the likelihood of similar incident happening.
