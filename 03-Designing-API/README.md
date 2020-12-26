# 03 Designing APIs

> Spec Driven Development - first, create the specification for the API; then build the code to match the spec

Steps refresher:

* Design
* Simulate
* Feedback
* Validate

## Options to define API design

* Hand Coding (so when a dev is building an API. Mule thinks it's outdated...)
* API Blueprint (using Markdown - Apiary)
* OpenAPI Spec (JSON-Based - Swagger)
* RAML

## RAML

RAML - **R**estful **A**PI **M**odeling **L**anguage

* Non-proprietary, vendor-neutral open spec
* Files can be used to auto-generate docs, mocked endpoints, interfaces for API implementations etc.
* Loosely based on `YAML`

### Defining resources and methods

* Resources are the objects identified by the web service URL that you want to act upon using the HTTP method used for the request
* All resources begin with a slash
* Any methods and parameters nested under a resource belong to and act upon that resource
* Nested resources are used for a subset of a resource to narrow it
  * URI parameter are enclosed in `{}`

## Testing

Can be done using the **API Console** and the **mocking service** to run a live simulation.

Mocking is available to outside stakeholders through shareable links with optional expiration date.

API Console is available in:

* API Designer - so the API designer can test
* API Portals in Exchange - so the users/developers can test

## Defining examples

Can be done using

* `example` - to represent a single instance of the data
* `examples` - to represent multiple instances of the data

> Both are using k/v pairs

`RAML` can be fragmented. Fragments can be:

* Data type
* Examples
* Traits
* Resource types
* Overlays
* Extensions
* Security
* Schemes
* Documentation
* Annotations
* Libraries

Fragments can be stored:

* In different files and folders within a project
* In a separate API fragment project in Design Center
* In a separate RAML fragment in Exchange

---

## Quiz

1. An API has been created in Design Center. What is the next step to make the API discoverable?

> Publish the API from inside Flow Designer

2. Refer to the exibit. What is the correct URL to submit a GET request to `/patients`?

```YAML
#%RAML 1.0
title: ACME Medical API
baseUri: http://dev.acme.com/api

/patients:
  get:
    queryParameters:
      year:
        type: integer
        example: 2017
```

> http://dev.acme.com/api/patients?year=2016

3. A RAML example fragment named BandAccountsExample.raml is placed in the examples folder in an API specification project. What is the correct syntax to reference the fragment?

> examples: !include examples/BankAccountExample.raml

4. Refer to the exibit. There is an error in the `flight_id` resource's GET method. What needs to be done to fix the problem?

```YAML
#%RAML 1.0
version: v1
title: American Flights API

/flights:
  get:

  /{flight_id}:

get:
```

> Indent the get method under the {flight_id} resource

5. Refer to the exhibit. This RAML specification includes an XML example that matches the Records data type defined in another RAML file named recordsDataType.raml. Using the Records type, how can this XML example be represented in RAML?

```YAML
#%RAML 1.0
title: Records API

/records:
  get:
    responses:
      200:
        body:
          application/xml:
            example: |
              <music>
                <collection>Deep Collection</collection>
                <artists>
                  <artist1>Deep Purple</artist1>
                  <artist2>Rainbow</artist2>
                </artist>
              </music>
```

> Answer below

```YAML
#%RAML 1.0
title: Records API

types:
  Records: !include recordsDataType.raml

/records:
  get:
    responses:
      200: 
        body:
          application/xml:
            type: Records
            example:
              music:
                collection: "Deep Collection"
                artists:
                  artist1: "Deep Purple"
                  artist2: "Rainbow"
```
