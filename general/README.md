Finshift  
Application
===========

## Overview
Finshift is the vanguard of personal financial transformation, redefining the way you manage, invest and grow your wealth. Combining the most advanced Quantitative Finance techniques with cutting-edge Artificial Intelligence algorithms, Finshift offers personalized insights, proactive recommendations and optimized strategies to maximize your financial health. In addition to helping with tracking expenses and defining budgets, the system provides in-depth analysis, aligning investment recommendations with your profile and financial objectives. With dedicated AI assistants for wealth management, financial analysis, and investments, every aspect of your financial life gets the attention and expertise it deserves. At Finshift, your data security is a priority, ensuring your financial information remains private and protected. More than an app, Finshift is your financial partner, guiding and propelling you towards a brighter, more prosperous financial future.

&nbsp;

## A slightly more technical and less commercial presentation
Finshift is an advanced financial platform designed to provide users with optimized financial management. Using modern Quantitative Finance techniques combined with Artificial Intelligence algorithms, the system aims to transform the traditional approach to financial management into a more intuitive and effective experience.

Finshift's main objective is to empower the average user with tools and insights that would traditionally only be available to finance experts. By automating and optimizing many of the traditional financial processes, Finshift seeks to transform the way individuals manage and invest their money, leading them to achieve their financial goals more effectively, as well as enrich themselves through financial tweaks, investment advice, AI investment analysis with advanced Quantitative Finance algorithms, etc.

&nbsp;

## Features (In order of development)

### Accounts
- Common feature just to register and sign in the user in the system

### Budget
- Tool to create and manage monthly, annual or personalized budgets.
- Alerts when users are getting close to or exceeding their limit.

### Financial Goals Planning
- Definition of financial goals and action plan to achieve them.
- The highlight goes to the action plan, which must be built with AI assistance

### Debt and Financing Management
- Tools to manage debts, loans and financing, with details on interest rates, terms and future payments.
- This part must be integrated into the Budget and a calculation must be made of the impact that this debt has on the monthly and annual budget and financial goals

### Income and Expenses
- Registration and categorization of income and expenses.
- Connection with bank accounts for automatic import of transactions.

### Integration with Other Platforms
- Integration with banks, brokers, payment apps and other financial platforms for a holistic view of finances.

### Reports and Analysis
- Graphs and reports on income, expenses, cash flow and net worth.

### Interactive Dashboard
- Overview of user finances: assets, liabilities, income, expenses, investments and financial goals.
- This dashboard will evolve as the user advances in their financial planning, accumulates more capital, has more investments, because in the beginning, generally, for the middle class user, there is no rent to receive, there are no investments in shares , FIIs, or anything like that

### Property and Tangible Asset Management
- Tools to manage and track properties and other tangible assets such as vehicles and collectibles.

### Alerts and Notifications
- Notifications about bill payments, goals achieved and other relevant information.

### Security
- Measures such as end-to-end encryption and two-factor authentication.

### Backup and Restore
- Ensure that user data is secure and can be restored if lost.

### Customer Support
- An effective support channel to help users with questions or problems.

### Accessibility
- The platform must be accessible on mobile and desktop devices, with a UX optimized for both.

### Development of FinManage V1 AI (FinManage V1 is the AI for level 1 asset management, which has more restricted functionalities)
- AI to make payment schedules, automated payments, carry out banking operations, etc. (we will define the list of features later)

### Development of FinAnalytics V1 AI (FinAnalytics V1 is AI for level 1 financial analysis, which has more restricted functionalities)
- AI to search for bank statements and financial movements, in-depth analysis of movements and contrast with global financial planning, medium and short term planning, etc. (we will define the list of features later)

### Personalization
- The ability to customize the interface, reports and analytics according to user preferences and needs.

### Financial Education
- Educational content on basic and advanced financial topics.

### Investment Analysis
- Tracking and analyzing investments such as stocks, bonds and mutual funds.

### Financial Calculators
- Tools for calculations related to interest, loans, mortgages and retirement.

### Development of FinStEx V1 AI (FinStEx V1 is the AI for level 1 investments, which has more restricted functionalities)
- AI to search for bank statements and financial movements, in-depth analysis of movements and contrast with global financial planning, medium and short term planning, ... (we will define the list of features later)

### Retirement Planning
- Calculators and tools to help users plan their retirement, considering inflation, life expectancy, among other factors, always based on the current budget, future budget projections, financial goals, etc.

### Tax Planning
- Tools and information to help users optimize their tax situation.

&nbsp;

## AI Assistants

### FinManage -> AI for Wealth MManagement (Has levels L1, L2 and L3)
- Features: Payment scheduling, integrations with banks, bank transfers, verification of tax commitments, accounting issues, and other resources related to asset management.
- Technology: Can use Natural Language Processing (NLP) techniques to understand and process user commands, in addition to integrations with banking and tax APIs.

### FinAnalytics -> AI for Financial Analysis (Has levels L1, L2 and L3)
- Features: Analysis of financial transactions, suggestions for improvements, proposals for debt payment, and other financial insights.
- Technology: Machine learning algorithms for analyzing spending patterns and recommendations.

### FinStEx ([St]ock [Ex]change) -> AI for Investments (Has levels L1, L2 and L3)
- Features: Analysis of historical series, fundamental analysis, investment recommendations based on quantitative finance.
- Technology: Advanced machine learning algorithms and quantitative analysis, integration with asset databases and financial markets.

&nbsp;

## Audience Segmentation

###  Plan 'Foundation'
- Target audience: Middle class.
- Features: Basic finance management, budgets, expense tracking, insights into consumption habits, and basic investment recommendations.
- AI Assistant: May include a more basic version of the wealth management (L1) and financial analysis assistant (L1).

### Plan 'Performance'
- Target audience: Class A.
- Features: All those of the normal plan, plus advanced asset management, more detailed investment analysis, integrations with more banks and brokers, and additional features such as tax and fiscal planning.
- AI Assistant: More advanced versions of the wealth management (L2) and financial analysis (L2) assistants, in addition to a basic version of the investment assistant (L1).

### Plan 'Fortune'
- Target audience: People who manage large fortunes.
- Features: All of the previous plans, plus family wealth management, succession planning, international investment analysis, and other exclusive features for this segment.
- AI Assistant: All three AI assistants in their most advanced and personalized versions (L3).

&nbsp;

## Project specifications
- All source code must be written in English (classes, methods, variables, database schemas, code comments, etc.)
- API returns must be made in English (all translation will be done on the frontend where we will use NextJS)
- All documentation will be in English
- The frontend will use an i18n lib to make available initially a version in English and Portuguese (Brazil)
- The Backend API documentation will be created using readme app (https://readme.com)

&nbsp;

## Infrastructure

### Overview
- Microservices architecture
- Internal communication made using gRPC
- Docker (1 container per service)

### Authorization Container
- Service dedicated to receive and filter all requests made against any of the services, authorize the access and use of the desired service resources, and redirect the request

### Application Containers
- Python
- Flask Framework
- SQLAlchemy
- Nginx as Reverse Proxy
- Gunicorn as WSGI server
- Pytest/Pytest-Flask (Unit tests and Integration tests)
- PostgreSQL

### Service Discovery Container
- Consul by Hashicorp

### Logging and Monitoring Containers
- Sentry for error logging (Sentry Server Service and Sentry SDK for Python within each container)
- Prometheus and Grafana for monitoring
- ELK Stack as a centralized logging storage

### Load Test Container
- Locust (Load test)

### DataLake Container
- MongoDB

&nbsp;

## Some artifacts
- FSLog - A logging library made specifically to meet the Finshift application needs. Created upon the Default Python Logging Library, will create logs in batch or not (depending the case) and in an asynchronous way (non-blocking), sending and storing the logs in the ELK Service

&nbsp;

## Application Services
1. Account
    - User registration (name, email, password)
    - Plan (Foundation, Performance or Fortune) - Free trial for 30 days
    - Password changing process (The user must validate the beginning of this process informing the current password. If it matches, the service will create a Validation Token (JWT) and send an email with a URL with this validation token. When the user clicks on the link he will be redirected to a page to change the password. This is a process that happens only after the user logs in)
    - Password recovery process (The user needs to validate the beginning of this process by informing the email. If it matches, the service will create a Validation Token (JWT) and send an email with a URL with this validation token. When the user clicks on the link he will be redirected to a page to change the password. This is a process that happens only with the user being logged out)
    - Account data update (name, email, password [through the password changing process specified previously], and other information that will be gathered in the Onboarding moment)
    - Account deletion (We will define after what to do here)
2. Authentication
    - SignIn (Email and Password)
    - SignOut
    - Two Factor Authentication (Email message)
3. Shared
    - User Session Management
4. Onboarding
5. Budget
6. Financial Goals (Short, medium, and long term. Including Retirement Planning)
7. Debt Management
8. Entry of Income and Expenses
9.  Integrations
    - Google ReCaptcha integration
10. Analytics
11. Dashboard
12. Tangible Asset Management
13. Notifications
14. Security
15. Backup
16. Support
17. Accessibility
18. FinManage
19. DataLake
20. FinAnalytics
21. Settings (Personalization, notifications, alerts, etc.)
22. Investment
23. FinStEx
24. Tax planning

&nbsp;

## DevOps
- GitHub Actions for CI and CD

## Development order (Just a proposal)
- Create the app folder structure
- Account Service Implementation
    - Create the service (Create the folder "/services/account" and inside it puts the requirements.txt, nginx.conf, other configuration or necessary files, and the Dockerfile. Include the service within the docker-compose.yml in the root)
- Working on the Account Service (The Account Service will be the base for the most of other services)
    - Implementation of the framework (Flask)
    - Implementation of the database (PostgreSQL)
    - Implementation of the SQLAlchemy
    - Implementation of the models
    - Execute the migrations and create the database structure
    - Implementation of the routes, endpoints, views, middlewares, security implementations, etc.
    - Implementation of the unit tests
- Service Discovery Service Implementation
    - Create the service (Create the folder "/services/discovery" and inside it puts the Dockerfile and any other thing required by the Hashicorp's Consul Lib. Include the service within the docker-compose.yml)
- Logging and Monitoring
    - Create the FSLog (stands for Finshift Log) Library, and we want this log flow in the application:
    
            Asynchronous Logging Flow with ELK Stack:
            
            1. Custom Logging Library:
            - Develop a custom logging library that encapsulates the standard Python logging module.
            - This library should support asynchronous logging operations, allowing log messages to be buffered and processed in batches or individually as needed.
            
            2. Buffering and Asynchronous Logging:
            - Use buffering to collect and temporarily store log messages before sending them to the centralized storage system.
            - Implement asynchronous logging to ensure that log writing doesn't block or delay other application operations. Log messages can be placed in a queue and processed in the background, either in batches or individually.
            
            3. Integration with ELK Stack:
            - Configure the library to send logs to the ELK Stack (Elasticsearch, Logstash, Kibana) for centralized storage, analysis, and visualization.
            - Use Logstash or Filebeat to collect and send logs to Elasticsearch.
            - In Elasticsearch, logs will be indexed and stored, allowing for fast queries and detailed analysis.
            - Use Kibana to visualize and analyze the logs, create custom dashboards, and set up alerts for specific events.
            
            4. Flexibility and Configuration:
            - The library should allow for flexible configurations, such as adjusting the buffer size, setting the batch log send interval, and specifying the log level (INFO, ERROR, DEBUG, etc.).
            - Provide options to handle send failures, such as retry attempts or temporary local storage.
            
            5. Security and Compliance:
            - Ensure logs are transmitted securely, using encryption in transit.
            - Implement access controls in the ELK Stack to ensure only authorized personnel can view or modify the logs.
            
            6. Monitoring and Alerts:
            - Use Kibana to set up real-time alerts for critical events or suspicious patterns in the logs.
            - Monitor the health and performance of the logging system to ensure ongoing availability and efficiency.
    - Prometheus Implementation
        - Create the service (Create the folder "/services/prometheus" and inside it puts the Dockerfile and the Prometheus config file. Include the service within the docker-compose.yml)
    - Grafana Implementation
        - Create the service (Create the folder "/services/grafana" and inside it puts the Dockerfile. Include the service within the docker-compose.yml)
- Load Test Implementation
    - Create the service for Locust (Create the folder "/services/loadtest" and inside it puts the Dockerfile and any other necessary file. Include the service within the docker-compose.yml)