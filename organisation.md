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

Planned Github project organisation is shown below:

| Repository      | Description |
| --------------- | ----------- |
| [HTRC-Core](https://github.com/htrc/HTRC-Core)            | Parent repo containing build scripts, local deployment scripts and integration tests for core services. Core components are added as submodules and these submodules always linked to a stable tag. |
| [HTRC-WSO2IdentityServer](https://github.com/htrc/HTRC-WSO2IdentityServer)         | Custom WSO2 IS build for HTRC with registry related features, Registry-Extension and HTRC specific extensions.   |
| [HTRC-DataAPI](https://github.com/htrc/HTRC-DataAPI)        | HTRC Data API |
| [Agent](https://github.com/htrc/Agent)           | HTRC job management API |
| Data-Capsule-API | HTRC Data Capsule VM managmeent API |
| Portal          | HTRC Portal |
| Workset-Builder | HTRC Workset Builder |
| Feature-API     | Serve features extracted from HTRC corpus including copyrighted content |
| Algorithms      | Text processing/analaysing algorithms provided by HTRC |
| [HTRC-Commons](https://github.com/htrc/HTRC-Commons)         | Re-usable libraries for HTRC services and other text analysis related tasks |
| Tools           | Various tools provided to HTRC users |
| SDK             | HTRC Software Development Kits for Python, R and other languages |
| Samples         | Sample code/scripts related to HTRC tutorials and documentation |
| Workshops       | HTRC workshop materials |

  > We are still in the process of moving from Sourceforge to Github. Current state of HTRC Github organisation may not look like above. But we are working on to get HTRC organisation to have above mentioned individual orjects.

HTRC developers are encouraged to follow below guidelines and best-practices when creating projects, moving existing projects to new locations and doing releases to individual components.

- **When adding submodule, its storngly advised to link to a stable tag**.
- Core services and font-end services have their own Github repositories.
- Parent HTRC-Core repo links to individual core services repos using git submodules and these submodules should link to stable tag of core service, not to the master branch.
- Common libraries used accross HTRC software stack goes inside HTRC-Commons project.
- HTRC algorithms related code goes inside HTRC-Algorithms project.
- HTRC SDKs and Tools will have their own repositories. Same for Internal Tools.
- Internal Tools repository is a private repository only accessible to HTRC team members.
- In cases where developers needed to manage source of a module which can come under HTRC-Commons, Algorithms, Tools and SDKs as separate project, its strongly recommended to add this individual repository as a submodule to the parent repo.



