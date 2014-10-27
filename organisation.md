---
layout: page
title: Project Organisation
---

This document is a recommendation by the HTRC Core Development team on the use of the HTRC GitHub Repository.  The goal with this new repository organization is twofold:  separation of functionality to improve extensibility, and better separation of core functionality to support continuous integration and testing.   The document is the product of the HTRC Core Development team; questions should be addressed to them.

We can categorize the current software modules in HTRC as follows.

- **Core Services**: The whole HTRC software stack is built on top of several core services (Identity Provider + Registry, Data API, Agent, Data Capsule API). All the other components are built on top of these components.
- **Front-end Services**: Users directly interact with these components. Portal, Workset Builder, Feature API like components comes under this category.
- **Common Libraries and Utilities**: These components are shared across *core services*, *front-end services* and other components in HTRC. They mainly contains re-usable code/APIs.
- **Internal Tools**: Tools used by HTRC staff to carry out administrative tasks such as monitoring, user management, deployment, migration. Best example is *Log Analyzer* used by IU team.
- **HTRC SDKs**: When users of HTRC wanted to interact with HTRC system or wanted to submit jobs which interacts with HTRC services, they need these HTRC implemented *software development kits* which provides the standard APIs to interact with HTRC. For example, we can create a Python library which allows users to interact with HTRC APIs such as *Feature API*. This library will encapsulate the functionality required to acquire necessary security tokens and invoke the API with the token.
- **Samples and Workshop Material**

Based on the above categorization, we can categorize HTRC services[^1] as follows.


| **Core Service** | **Front-end**   | **Common**            | **Internal** | **SDKs**   |
|------------------|-----------------|-----------------------|--------------|------------|
| IS + GREG[^2]    | Portal          | OAuth2 Servlet Filter | Log Analyzer | Python SDK |
| Data API         | Workset Builder | Registry API Client   |              | R SDK      |
| Agent            | Bookworm        | Agent API Client      |              |            |
| Data Capsule     | Feature API     |                       |              |            |
| IPython API      | Solr Proxy      |                       |              |            |
