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

### Entrypoint Container
- Service dedicated to receive and filter all requests made against any of the services, authorize the access and use of the desired service resources, and redirect the request (Basically this will have a Nginx as reverse proxy and perform API authentication using JWT)

### Services Containers (This is the default structure for all containers that will handle the services) - We will have a bunch of this kind of container, one for each service (will be listed and described after)
- Python
- Flask Framework
- PostgreSQL
- SQLAlchemy
- Gunicorn as WSGI server
- Sentry SDK (will connect with the Monitoring Container)
- Pytest/Pytest-Flask (Unit tests and Integration tests)

### Service Discovery Container
- Consul by Hashicorp

### Monitoring Container
- Sentry for error logging (Sentry Server Service and Sentry SDK for Python within each container)
- Prometheus and Grafana for monitoring

### Logging Container
- ELK Stack as a centralized logging storage

### Load Test Container
- Locust (Load test)

### DataLake Container
- MongoDB

&nbsp;

## Custom Libraries
- FSLog - A logging library made specifically to meet the Finshift application needs. Created upon the Default Python Logging Library, will create logs in batch or not (depending the case) and in an asynchronous way (non-blocking), sending and storing the logs in the ELK Service

&nbsp;

## Services (I have the description just for the Account Service, Authentication Service, and Shared Service [store the user session]. I will update this documentation after, describing the other services that is without description right now)
- Account
    - User registration (name, email, password)
    - Plan (Foundation, Performance or Fortune) - Free trial for 30 days
    - Password changing process (The user must validate the beginning of this process informing the current password. If it matches, the service will create a Validation Token (JWT) and send an email with a URL with this validation token. When the user clicks on the link he will be redirected to a page to change the password. This is a process that happens only after the user logs in)
    - Password recovery process (The user needs to validate the beginning of this process by informing the email. If it matches, the service will create a Validation Token (JWT) and send an email with a URL with this validation token. When the user clicks on the link he will be redirected to a page to change the password. This is a process that happens only with the user being logged out)
    - Account data update (name, email, password [through the password changing process specified previously], and other information that will be gathered in the Onboarding moment)
    - Account deletion (We will define after what to do here)
- Authentication
    - SignIn (Email and Password)
    - SignOut
    - Two Factor Authentication (Email message)
- Shared
    - User Session Management
- Onboarding
- Budget
- Financial Goals (Short, medium, and long term. Including Retirement Planning)
- Debt Management
- Entry of Income and Expenses
-  Integrations
    - Google ReCaptcha integration
- Analytics
- Dashboard
- Tangible Asset Management
- Notifications
- Security
- Backup
- Support
- Accessibility
- FinManage
- DataLake
- FinAnalytics
- Settings (Personalization, notifications, alerts, etc.)
- Investment
- FinStEx
- Tax planning

&nbsp;

## DevOps
- GitHub Actions for CI and CD
