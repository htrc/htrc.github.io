---
layout: page
title: Developer Guidelines
---

This document contains set of guidelines, recommendations and best practices by
HTRC Core Development team on

*  the use of git repositories under [HTRC Github](http://github.com/htrc)
account
*  creating new projects
*  adding modules to existing projects

These guidelines are meant to encourage consistency and best practices amongst
people working on the HTRC code base. They should be observed unless there is a
compelling reason to ignore them.

```
The document is the product of the HTRC Core Development team; questions should be addressed to them.
```

## Github Projects

Described below are set of guidelines and best practices to follow when
creating/migrating Github repositories which comes under HTRC organisation.
These guidelines and best practices are based on *HTRC Component Categorization*
listed below.

- **Core Services**: Foundation of HTRC software stack -- *Identity Provider + Registry*, *Data API*, *Agent*, *Data Capsule API*. Front-end components, SDKs built on top of services provided by these components.
- **Front-end Services**: Users directly interact with these components. Portal, Workset Builder, Feature API like components comes under this category.
- **Algorithms**: HTRC provided text processing/analysis algorithms.
- **Common Libraries and Utilities**: These components are shared across *core services*, *front-end services* and other components in HTRC. They mainly contains re-usable code/APIs.
- **Tools**: Various tools provided by HTRC to make user's life easier.
- **HTRC SDKs**: When users of HTRC wanted to interact with HTRC system or wanted to submit jobs which interacts with HTRC services, they need these HTRC implemented *software development kits* which provides the standard APIs to interact with HTRC. For example, we can create a Python library which allows users to interact with HTRC APIs such as *Feature API*. This library will encapsulate the functionality required to acquire necessary security tokens and invoke the API with the token.
- **Internal Tools**: Tools used by HTRC staff to carry out administrative tasks such as monitoring, user management, deployment, migration. Best example is *Log Analyzer* used by IU team.
- **Samples**: Sample code related to HTRC tutorials, documentation and etc..
- **Workshop Material**: Resources from HTRC related workshops.

Based on above categorization we have the following Github repositories which
contains various parts of the HTRC software stack. Some basics behind this
repository structure:

- All the core services will get its own repo, but there will be a parent
repo which links to these core services via git *submodules* and contains
build scripts, integration tests and docker based HTRC Core local deployment scripts.
- All the front-end modules will have their own repositories.
- Common libraries will go under *Commons* repository.
- All the algorithms will come under *Algorithms* repository.
- HTRC SDKs and Tools will have their own repositories. Same for Internal Tools.
- In cases where modules belong to Core, Common, Algorithms, SDKs, Tools need their
own repository, they **should be added to relevant parent repo as a submodule**.
- When adding submodules, its recommended to link to a **stable tag**.

### Github Structure

| Repository      | Description |
| --------------- | ----------- |
| Core            | Parent repo containing build scripts, local deployment scripts and integration tests for core services. Core components are added as submodules and these submodules always linked to a stable tag. |
| IS+GREG         | Custom WSO2 IS build for HTRC with registry related features, Registry-Extension and HTRC specific extensions.   |
| Data-API        | HTRC Data API |
| Agent           | HTRC job management API |
| Data-Capsule-API | HTRC Data Capsule VM managmeent API |
| Portal          | HTRC Portal |
| Workset-Builder | HTRC Workset Builder |
| Feature-API     | Serve features extracted from HTRC corpus including copyrighted content |
| Algorithms      | Text processing/analaysing algorithms provided by HTRC |
| Commons         | Re-usable libraries for HTRC services and other text analysis related tasks |
| Tools           | Various tools provided to HTRC users |
| SDK             | HTRC Software Development Kits for Python, R and other languages |
| Samples         | Sample code/scripts related to HTRC tutorials and documentation |
| Workshops       | HTRC workshop materials |
