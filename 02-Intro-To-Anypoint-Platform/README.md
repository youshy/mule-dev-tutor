# 02 Introducing Anypoint Platform

1 Design Center - 1 Management Center - 1 Runtime

## Layer Benefits

* Speed of delivery
* Actionable visibility
* Secure by design
* Future-proof architecture
* Intentional self-service

## Catalyst approach

> https://catalyst.mulesoft.com

* Business outcomes - Define outcomes with clear KPIs and align stakeholders
* Technology delivery - Get up and running with Anypoint Platform and start building APIs and integrations
* Organisation enablement - Ensure your organisation is ready to use and adopt the Anypoint Platform

## MuleSoft blueprint

|       | **Plan for success** | **Establish the foundation** | **Build to scale** | **Measure impact** |
| :---- | :----: | :----: | :----: | :----: |
| **Business outcome** | Agree on business outcomes and KPIs; Develop the overall success plan | Monitor and manage | Refresh the success plan | Measure business outcomes |
| **Technology delivery** | Define anypoint platform vision and roadmap; Design Anypoint platform architecture and implementation plan | Deploy Anypoint Platform | Refine and scale Anypoint Platform | Measure Anypoint platform KPIs |
| **Technology delivery** | Prioritise IT projects and quick wins; Staff and onboard the project teams | Define reference architecture; Launch initial projects and quick wins | Onboard additional project teams; Launch additional projects | Measure project KPIs |
| **Organisational enablement** | Assess integrational capabilities; Establish the C4E operating model | Build and publish foundational assets; Evangelise | Drive consumption | Measure C4E KPIs |
| **Organisational enablement** | Onboard MuleSoft; Determine the internal support operating model | Staff, train and launch team; Publish support guidance and self-serve materials | Monitor Anypoint Platform | Measure support KPIs |
| **Organisational enablement** | Agree on initial roles; Train the initial team(s) | Develop the broader training plan; Launch experiental learning opportunities | Update training plan | Conduct skills assessment |

## API Development Cycle

> Described using tools provided by MuleSoft

### API Specification

* Design
    * API Designer - used to describe the contract that provides all of the details of operations, inputs and outputs
* Simulate
    * API Console & Mocking Service - used to mock the API and the interactions with it. 
* Feedback
    * API Portal & Exchange - used to publish the API and allow to make the API discoverable
* Validate
    * API Notebook - can be added to the Portal w/ JavaScript code snippets

Output: API Spec in `.RAML` service

### API Implementation

* Build - using Anypoint Studio (building by importing the `.RAML`
* Test - using MUnit suite, provides unit test functionality

### API Management

* Version
* Secure
* Deploy & Register
* Monitor
* Analyse
* Troubleshoot
* Scale
* Respond

Output: Web Service with API

* API Manager is used to Version and Secure the API by creating policies
* Runtime Manager is used to Deploy & Register, Monitor (also provided by Anypoint Monitoring), Analyse and Troubleshoot
* Visualiser provides a real-time visualisation of the API

## Anypoint Exchange

Provides all users a library of assets that links to Consumption (Feedback and usage metrics) & Production (Reusable assets) model. Exchange ensures that assets are published somewhere they can be discovered and reused.
Supports private assets as well.

Whenever a REST API is added to exchange, an **API portal** is automatically created for it.

API portal contains of:

* Auto-generated **API documentation**
* An **API console** for consuming and testing APIs
* An **automatically generated API endpoint** that uses a **mocking service** to allow the API to be tested without having to implement it

When a RAML 1.0 API specification is added to Exchange, a **connector** is automatically created for it. Connector can be used in Mule applications to make calls to that API.
