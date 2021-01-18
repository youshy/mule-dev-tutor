# Benefits of application networks and API-led connectivity

## API design-first approach lifecycle:
- IT build reusable APIs & services for accessing data and resources
    - BUILD: Design - Simulate - Feedback - Validate - Test
- These are available for consumption - enable business to self serve using core assets
    - RUN: Web service with API - monitor, feedback, scale 
-   Consumers give active feedback which, alongwith usage metrics, feeds change 
    - OWN: IT responds to organisation needs repeating lifecycle.

### Mule provides a tool and approach for reuse, enhances speed in response to high rate of change.

### Decouples data sources -> application direct connections

### Reusable, discoverable self service API - security, scaleable and performant. 

What | Example | Who | Trait
-----| ---- | ----- | -----
SYSTEM API| SAP, Salesforce, DB |Central IT|  UNLOCK
PROCESS API| customers / orders from multiple sources |LOB|  COMPOSE
EXPERIENCE API| web app API / mobile app |Developers|  CONSUME

An experience API will make requests to existing reusable process & business APIs, fed by system APIs. 
Governance and transparency is provided via monitoring, feedback from consumers triggers changes. 

![API Led connectivity](/images/API-led-connectivity.png)

# C4E - Center for enablement is a cross functional team to ensure assets are:
     - productized and published
     - consumable
     - fully leveraged by Lines of Business
### Success is asset consumption. 
__Role in new IT operating model "Creates and manages discoverable assets to be consumed by LOB developers"__

# Application Network
    - every new node or API adds value to multiple systems as is connected
    - other applications connect and consume endpoints
    - recomposable "bends not breaks - built for change"
*Innovates* 

# API
Provides information for __how to communicate with software component__ it is __independent of component implementation__

    - Operations (what it does - endpoints to call)
    - Inputs (what you send)
    - Outputs (what you get back)
    - Underlying datatypes
It is an interface to a functionality which can be changed, without the calls changing. 

API refers to: 

    - API definition /Spec 
    - API web service you make calls to
    - API proxy which restricts access and usage.
Can be:

    -   SOAP - XML based wsdl & HTTP    
    -   REpresentational State Transfer - HTTP request method indicates operation per URL.
Accessed by: 
```
(GET)/companies
(GET)/companies?country=France  - query parameters
(GET)/companies/3   - URI parameters

GET - RETRIEVE,  POST - CREATE, DELETE, PUT - REPLACES OR CREATES, PATCH - PARTIAL UPDATE OF EXISTING. 


Response formats - JSON, XML , collections & maps
```
[Status Codes](https://httpstatus.io/http-status-codes)

Security:
```
Unsecured 
    - public with no authentication

Secured - authentication via:
            - credentials and / or token
            - proxy may govern access
            - protocols e.g. OAuth, SAML, JWT.. 
```

## Anypoint platform: 
    - central repo for discovery & reuse of assets
    - build applications to consume assets  & connect systems
    - complete API development lifecycle

# Quiz 1

Q: What MuleSoft API-led connectivity layer is intended to expose part of a backend database without business logic?
A: System

Q: What statement is part of MuleSoft's description of an application network?
A: Creates reusable APIs and assets designed to be consumed by other business units

Q: According to MuleSoft, what is the Center for Enablement's role in the new IT operating model?
A: Creates and manages discoverable assets to be consumed by line of business developers

Q: What is a core characteristic of the Modern API?
A: API is designed first using an API specification for rapid feedback
