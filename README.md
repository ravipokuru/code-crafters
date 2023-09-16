**Team Members**
 
Bramhchariya, Ujjwal

Maram Prathyusha

Prasad, Thiragabathina

Singh, Kamal Deep

Swaroop, Abhigyan
















**Contents**

- **Introduction**
- **Company Vision**
- **BRD**
  - **Requirements**
  - **Tech Constraints**
  - **Business Constraint**
  - **Key Assumptions**
- **Architecture Characteristics**
  - **Data Integration & Aggregation**
  - **Usability**
  - **Flexibility**
  - **Scalability**
  - **Portability**
  - **Availability**
  - **Performance**
  - **Security**
  - **Cost**
  - **Localization**
  - **Error Handling**
- **Architecture Approach**
- **Logic Behind this Approach**
- **Methodology**
- **CNCF Recommendation**
- **Cloud Native 12 Factors**
- **Microservices – Essential Components**
- **The Road Warrior Conceptual Architecture**
- **The Road Warrior Logical Architecture**
- **Components**
  - **Identity Manager**
  - **Email Polling**
  - **Notification Services**
  - **UI Layer**
  - **API Layer**
  - **Analytics**
  - **Time Localization**
  - **Social Media Plugins**
- **Deployment**
- **Cost Analysis**
- **Evaluation, Risk and Arch Fitness**






**Introduction**

The Road Warrior is a Tech Start Up which is very passionate to upscale users Travel Experience with Real-Time Personalized Unified Dashboard on our fingertips.

It’s App empowers users to get Real-Time updates on their Travel Related itinerary across all channels and vendors.

Be it update to flight schedules or the finer details of hotel check-ins, our platform employs diverse notification mechanisms to ensure travellers are in the know. Moreover, we're here to facilitate the joy of sharing these moments with friends on social media, transforming individual experiences into shared memories.

**Company Vision**:

Embracing a vision of empowerment, Road Warrior sets out to redefine travel experiences. We strive to offer travellers a seamless, personalized, and real-time trip management solution, revolutionizing the entire journey - from planning to cherishing every moment

**BRD**

**Requirements**

Build the next generation online trip management dashboard to allow travellers to see all their existing reservations organized by trip either online (web) or through their mobile device. 

Detail Use Case can be found HERE

**Technical Constraint**

- This is a greenfield technical project, the only assumed constraint is lack of existing infrastructure
- Finding Right people for the job (Developers)

**Business Constraint**

- Seed fund
- Revenue Model: Strategizing revenue generation through subscriptions, transaction fees, and partnerships with third parties
- Global Adaptability: Adapting the platform for diverse audiences, including different currencies and languages.

**Key Assumptions**

- The system doesn’t support Travel Booking services
- The system doesn’t support travel updates services
- The system doesn’t support financial transactions
- Travel Vendors have Near Real Time API exposed for Data Consumption
- SABRE/APOLLO have Near Real Time GDS API exposed for Data Consumption
- Email Forwarding functionality is not considered. (Suggested to have)
- Development team size in consideration 4-6 developers

**Architecture Characteristics**

- **Data Integration and Aggregation**

The system needs to connect to multiple sources (email clients, diff travel agents, Sabre/Apollo GDS) to retrieve airline, hotels and cab booking details. To maintain up-to-date information on availability, and other travel-related details.

The system needs to normalize data from these various sources into a consistent format, making it easier to compare and display information to users

- **Usability**

It is important for travel systems to be usable because they are used by a wide range of people. The need for it to be intuitive and usable is implicit.

Mobile apps should leverage device-specific features like GPS for location-based recommendations, push notifications for updates.

- **Flexibility**

As the startup grows the system should be able to adapt to business features and technologies.

Architecture that requires heavy upfront investment in hardware or software or long-term licencing should be avoided if possible.

Must document processes, requirements, and architectural decisions, to make a complete rewrite of software component, a viable option.

- **Scalability**

Travel systems must handle fluctuating loads, especially during peak travel seasons. Needs to design system that can scale horizontally to accommodate increased demand. SaaS Vendor should provide assurances of scalability. And explain how they stress test their infrastructure

- **Portability**

We need to avoid vendor or technology lock-in as the system scales to serve a growing user base

- **Availability**

The systems needs to be available at all times or no real time down time. The system needs to have the below techniques in place to ensure high availability:

Redundancy, load balancing, failover mechanisms, and disaster recovery plans.

- **Performance**

Travel systems needs to ensure that the platform operates efficiently, meets user expectations, and handles varying loads effectively. 

System needs to enforce explicit architecture fitness functions on certain components, that could monitor response times and raise alerts.

Customer interactions should be fast to provide a good customer experience.** In rare cases where it takes longer, a progress indicator and other interactive elements should be used to maintain a smooth user experience.

Usage of CDNs to serve static assets and improve the loading speed of web pages.

System must implement query caching to improve the response times.

APIs of data sources like email clients, travel agencies, Sabre/Apollo GDS may have rate limits. The system must manage API requests effectively to avoid overloading partners.


- **Security**

Travel systems must be secure from cyberattacks and other malicious threats. This can be achieved by using strong authentication and authorization mechanisms, and by encrypting sensitive data.

There is need for masking and anonymization of sensitive data in non-production environment to minimize risk during development and testing.

Ensure compliance with regulatory requirements, such as GDPR or CCPA, to ensure the privacy and rights of users. The SaaS vendors must also be reputable and provide security assurances.


- **Cost**

This project is start-up business. Cost of development, infrastructure requisition and maintenance are implicit concerns.

- **Localization & Global Reach**

System should support multiple languages. System will be setup in multiple data centres to ensure that users from various locations experience similar performance.

- **Error Handling and Recovery Procedures**  

The system should gracefully handle errors without prolonged downtime.

Monitor error rates and implement automated error recovery mechanisms.

The system should be responsible to taking backups of data, such that it may be restored to a working state in the event of failure


# **Architecture Approach**
###
### **Microservices Architecture**
A microservices architecture can be an effective approach for building a travel aggregator platform. Travel aggregators are complex systems that need to integrate with various data sources, provide real-time information, and deliver a seamless user experience. 












**Logic Behind this approach**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.001.png)







**Methodology**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.002.png)

**CNCF Recommendations**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.003.png)






**Cloud Native 12 Factors**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.004.png)

























**Microservices – Essential Components**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.005.png)

























**The Road Warrior Conceptual Architecture**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.006.png)


1. User Interface (UI):
   1. This is the frontend layer accessible to users through web browsers or mobile apps.
   1. It should be user-friendly, responsive, and offer features like search, booking, and account management.


1. Frontend Application:
   1. The frontend application handles user interactions, renders the UI, and communicates with the backend services.
   1. It may use modern web technologies or mobile app frameworks, depending on the platform.
1. API Gateway:
   1. Acts as a single entry point for all client requests and routes them to the appropriate backend services.
   1. Provides API versioning, security, rate limiting, and request/response transformation.
1. User Management and Authentication:
   1. Manages user accounts, authentication, and authorization.
   1. Ensures user data security and privacy.
1. Search and Aggregation Service:
   1. This service fetches and aggregates data from various sources, including airlines, hotels, car rentals, and travel agencies.
   1. It includes caching mechanisms to improve response times.
   1. May use APIs or web scraping techniques to gather data.
1. Search Engine:
   1. Utilizes advanced search algorithms to provide users with the best travel options based on their preferences.
   1. Handles filtering, sorting, and presenting results.
1. Notification Service:
   1. Sends email or push notifications to users regarding booking confirmations, changes, or updates.
1. Reviews and Ratings:
   1. Collects and displays user-generated reviews and ratings for hotels, airlines, and other services.
   1. May integrate with third-party review platforms.
1. Analytics and Monitoring:
   1. Collects data on user interactions, system performance, and errors.
   1. Provides insights to improve user experience and system efficiency.
1. Content Management System (CMS):
   1. Manages static content such as articles, blogs, and travel guides.
   1. Allows administrators to update and publish content.
1. Third-party Integrations:
   1. Integrates with external APIs for services like weather forecasts, visa information, travel insurance, and more.
   1. Ensures up-to-date information for travellers.




1. Database Layer:
   1. Utilizes relational databases (e.g., PostgreSQL, MySQL) and NoSQL databases (e.g., MongoDB) to store structured and unstructured data.
   1. Separates transactional data (e.g., bookings) and reference data (e.g., airports, cities).
1. Caching Layer:
   1. Implements caching mechanisms (e.g., Redis) to store frequently accessed data like search results, reducing load on backend services.
1. Content Delivery Network (CDN):
   1. Speeds up content delivery by caching and serving static assets (e.g., images, scripts) from edge locations.
1. Security and Compliance:
   1. Implements security measures like encryption (TLS/SSL), firewalls, and access controls.
   1. Ensures compliance with data protection regulations (e.g., GDPR).
1. Scalability and Load Balancing:
   1. Scales resources horizontally to handle varying levels of traffic.
   1. Distributes incoming requests evenly using load balancers.
1. DevOps and Deployment:
   1. Utilizes containerization (e.g., Docker) and orchestration (e.g., Kubernetes) for efficient deployment and scaling.
   1. Implements continuous integration/continuous deployment (CI/CD) pipelines.
1. Backup and Disaster Recovery:
   1. Implements regular backups of critical data and has a disaster recovery plan in place.
1. Monitoring and Logging:
   1. Monitors system health and performance in real-time.
   1. Logs events and errors for troubleshooting and auditing.
1. Documentation and Testing:
   1. Maintains comprehensive documentation for developers, operators, and support teams.
   1. Conducts thorough testing, including unit tests, integration tests, and performance tests.

Building a travel aggregator platform is a substantial undertaking, and it's essential to consider the specific needs of your target audience and regions of operation. Additionally, compliance with industry regulations and partnerships with travel providers are crucial factors to address.


**The Road Warrior Logical Architecture**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.007.png)





















**Components**

**Identity Manager**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.008.png)

SAML (Security Assertion Markup Language) is an open authentication standard that makes single sign-on (SSO) to web applications possible. SSO allows users to sign on to multiple web-based applications and services using a single set of credentials. Designed to simplify user sign-on experiences, SAML is most widely used in enterprise organizations and allows users to access applications and services that they pay for. 


Most importantly, SAML sign-on experiences are secure because user credentials are never transmitted. Instead, they’re handled by identity providers (IdPs) and service providers (SPs):


- The IdP stores all the user credentials and information necessary for authorization and provides it to the SP, when requested. It's the IdPs’ job to say, “I know this person, and they should be able to access these resources.” 
 
- The SP hosts the applications and services that users want to access. These applications or services might include email platforms, such as Google or Microsoft Office, or communications apps, such as Slack or Skype. It’s the SPs’ job to say, “You can access these applications or services for a specified period of time without having to sign-on again.”

When users attempt to access these applications or services, the SP asks the IdP to verify their identities. The IdP issues SAML assertions, or tokens, which contain the information necessary to confirm user identities, including the time the assertions were issued and the conditions that make the assertions valid. After they’re received, the SP gives users access to the resources they requested.



































**Email Polling**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.009.png)

Email polling is a method used in email communication to check for new messages or updates in an email inbox. It involves a client, typically an email client or application, periodically connecting to the email server to inquire if there are any new messages waiting to be retrieved. The client sends requests to the server at regular intervals to see if there are any new emails, and if there are, it downloads them to the client's inbox.

Here's how email polling typically works:

1. Client Configuration: The email client (e.g., Outlook, Thunderbird, or a mobile email app) is configured with the user's email account settings, including the email server's address (POP3 or IMAP server) and the login credentials.
1. Polling Interval: The user sets a polling interval, which determines how often the email client will check the server for new messages. Common polling intervals range from a few minutes to several hours, depending on the user's preferences.
1. Polling Process: At the specified intervals, the email client establishes a connection with the email server and sends a request to check for new messages.
1. Server Response: The email server responds to the client's request, indicating whether there are new messages or not. If there are new messages, the server provides information about them.
1. Message Retrieval: If new messages are available, the email client downloads them from the server and stores them in the user's inbox.
1. User Notification: Depending on the email client's settings, it may notify the user of new messages through pop-up notifications, sound alerts, or other means.

Email polling has been a common method for retrieving email for many years, particularly with POP3 (Post Office Protocol version 3) accounts. However, it has some limitations:

- Delayed Email Delivery: Since polling occurs at specific intervals, there may be delays in receiving new emails, especially if the polling interval is set to a longer time.
- Increased Server Load: Frequent polling can put additional load on email servers, especially for large organizations with many email clients checking for new messages.
- Battery Drain: On mobile devices, frequent email polling can consume more battery power, as the device needs to wake up and establish network connections regularly.

In contrast to email polling, modern email protocols like IMAP (Internet Message Access Protocol) and Exchange ActiveSync use a push mechanism, where the email server actively pushes new messages to the client as soon as they arrive, eliminating the need for polling and providing more real-time email delivery.
















**Notification System**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.010.png)














**UI Layer**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.011.png)

Inertia is a new approach to building classic server-driven web apps. We call it the modern monolith.

Inertia allows you to create fully client-side rendered, single-page apps, without the complexity that comes with modern SPAs. It does this by leveraging existing server-side patterns that you already love.

Inertia has no client-side routing, nor does it require an API. Simply build controllers and page views like you've always done! Inertia works great with any backend framework, but it's fine-tuned for Laravel.















**API Layer**

`                                         `**![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.012.png)**

Publish-subscribe messaging, or pub/sub messaging, is an asynchronous communication model that makes it easy for developers to build highly functional and architecturally complex applications in the cloud. In modern cloud architecture, applications are decoupled into smaller, independent building blocks called *services*. Pub/sub messaging provides instant event notifications for these distributed systems. It supports scalable and reliable communication between independent software modules.

The publish-subscribe (pub/sub) model enables event-driven architecture, which is required in several modern applications. You can use events to trigger and communicate between decoupled services. An event is a change in state, or an update, like an item being placed in a shopping cart.

Pub/sub messaging provides significant advantages to developers who build applications that rely on real-time events. 

We outline some of the advantages below:

***Eliminate polling***

Message topics allow instantaneous, push-based delivery, eliminating the need for message consumers to periodically check, or poll, for new information and updates. This promotes faster response time and reduces the delivery latency that can be particularly problematic in systems where delays cannot be tolerated.

***Dynamic targeting***

The pub/sub pattern makes the discovery of services easier, more natural, and less error-prone. Instead of maintaining a roster of peers so an application can send messages, a publisher will simply post messages to a topic. Then, any interested party will subscribe its endpoint to the topic and start receiving these messages. Multiple subscribers can change, upgrade, or disappear, and the system adjusts dynamically.

***Decouple and scale independently***

Pub/sub makes the software more flexible. Publishers and subscribers are decoupled and work independently from each other, which allows you to develop and scale them independently. You can decide to handle orders one way this month and then another the following month. Adding or changing functionality won’t send ripple effects across the system, because pub/sub allows you to flex how everything works together.

***Simplify communication***

Code for communications and integration is some of the hardest code to write. The publish-subscribe model reduces complexity by removing all the point-to-point connections with a single connection to a message topic. The topic will manage subscriptions to decide what messages should be delivered to which endpoints. Fewer callbacks result in looser coupling, plus code that is easier to maintain and extend.

***Durability***

Pub/sub messaging services often provide very high durability, and at-least-once delivery, by storing copies of the same message on multiple servers.

Security

Message topics authenticate applications that try to publish content and allow you to use encrypted endpoints to secure messages in transit over the network.













**Analytics/Reporting System**

`                          `**![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.013.png)**

**Time Localization**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.014.png)




**Social Media Plugins**

![](Aspose.Words.79a0fe65-b519-4cb5-9752-57429c20d2ce.015.png)

**Deployment**

Deployment is a critical phase in the software development process where you take your application or system from a development or staging environment and make it available for use by end-users or customers. The specific steps and strategies for deployment can vary widely depending on your technology stack, infrastructure, and project requirements. Below, I'll provide you with an overview of deployment documentation topics and some resources to help you get started.

**Deployment Planning:**

- Define your deployment goals and objectives.
- Identify the target environment (e.g., cloud, on-premises, hybrid).
- Determine the deployment strategy (e.g., blue-green, canary, rolling).
- Create a deployment timeline and schedule.

**Deployment Process:**

- Document the deployment workflow.
- Describe how code will be packaged and bundled for deployment.
- Specify any required build or compilation steps.
- Define the deployment scripts and automation tools (e.g., Ansible, Terraform, Docker, Kubernetes).

**Infrastructure Setup:**

- Specify the server or cloud infrastructure.
- Set up networking configurations.

**Deployment Monitoring and Rollback:**

- Detail how you will monitor the deployed application for performance and issues.
- Define thresholds and alerts.
- Document the rollback process in case of deployment failures.

**Security and Compliance:**

- Specify access controls and authentication methods.
- Ensure compliance with regulations (e.g., GDPR, HIPAA).

**Scalability and High Availability:**

- Describe strategies for scaling the application.
- Document redundancy and failover mechanisms for high availability.

**Backup and Recovery:**

- Document backup procedures for data and configurations.
- Define disaster recovery plans.


**Cost Analysis**

Actual cost of cloud services depends on implementation specific details such as network ingress/egress, CPU and memory usage etc, it can only be determined after building and staging the services on the clould platform.

An estimated Google Cloud cost analysis per month for 50000 Monthly active Users follows, obtained by pricing calculators for individual services

API gateway - 3000 calls per month per user $3 per million calls \* ((50000\*3000)/1000000) = $450

Cloud Run ~$50 \* 20 Instances - ~$1000 per month

Cloud SQL .035/GB/Hr \* 24 hrs \* 30 days \* 50 GB - $1260

Pub/Sub Lite (Throughput 1MBPS min/5 MBPS Max) with 1 day of storage - ~$70 per month

Total Estimated Cost per month 450 + 1000 + 1260 = $2780

**Evaluation, Risks and Architecture Fitness**

This final section is a discussion of how the proposed architecture adheres to the initially chosen driving characteristics, the associated trade-offs and risks. It highlights the areas that must continuously be tested and evaluated against benchmarks through fitness functions, ideally as part of the CI/CD pipeline.

*Evaluating the architecture against driving characteristics*

- Scalability - Domain functionality with high scalability requirements are isolated into stateless microservices. The Connections service is meant to be the most compute intensive, serving higher traffic than others, it is therefore designed to be stateless with no associated persistent data store. Fitness tests for scalability will involve running tests against staging clusters with simulated web traffic
- Performance - We mitigate network latency related performace issues with effective domain partitioning of data and services and avoiding distributed transactions. Individual services can be tested and benchmarked for performance
- Extensibility - The combination of Microservices, event driven communication and serverless deployment lends itself well to an extensible architecture, allowing new components and services to be introduced to serve additional requirements and use cases. However, it is difficult to test a system for extensibility, strict adherence to loose coupling and high cohesion between components is needed.

*Risks*

- Databases could be a bottleneck to horizontal scalability. Serverless database services/tools, shading and replication services/tools are possible mitigation strategies
- Testability of event driven workflows involving multiple services. Tests for individual microservices will also need to include comprehensive cases for distributed workflows








