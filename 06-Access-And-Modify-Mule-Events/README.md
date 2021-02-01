# Visibility of data passing through API

## Debug
* Run in debug 
    * Expand attributes, headers, queryParams
    * Add logger - view it's output in debug, console or log files
    * Port: 6666 app will stop at breakpoints or error handlers
    * Step through flow - using ARC increase request timeout to allow stepping e.g. 300000 ms

## View event data as it crosses transport boundary between flows. (via http Listener request / response or VM Connector)
* Scenario: Hello flow contains GET Request to Goodbye Flow 
(Request payload = Hello Response payload = Goodbye)
    * http://localhost:8081/hello?fname=dolly&lname=sheep
    * helloFlow payload is set Hello, at GET/goodbye -> goodbyeFlow
    * payload is set Goodbye, returns -> helloFlow payload still Goodbye
    * Response ```200 OK Goodbye```

* GET/hello HTTP Listener > Response
    * Set Headers e.g. "name" "Dolly", Body payload
    * response now includes ```name: Dolly```
    * Set response "name" to ``` "attributes.queryParams.fname" ```

* GET/goodbye HTTP Listener > Request 
    * Set query parameters Name:"fullName" Value:"Max Mule"
    * later set query parameters Name:"fullName" Value:"attributes.queryParams.fname"
    * THIS MANDATES query parameters are sent. Response 500 Server Error
    * Set default for fullName in setPayload ```[upper('Goodbye') ++ ' ' ++ attributes.queryParams.fullName default 'Dolly Sheep']```

## NOTE Flow references are calling a flow thus attributes, payload and variables are accessible
   A target variable in flow reference will set the target for return value e.g. flowReference.payload NOT flow.payload
## Dataweave
* expression and transformation language based on JAVA
    * usable from all event processors and global elements
    * evaluate data in payload, attributes and variables of Mule event, plus info re. Mule flow, instance and server e.g. OS, runtime ver., application name.
    * case sensitive
    * inline expressions #[]
    * standalone scripts
    * files ```.dwl```

* selectors
    * Single value #[payload.name]
    * Array index value #[payload[0].name]
    * Multi values of Array #[payload.*name]
    * Descendants recursively #[payload..zip]
* expressions - arithmetic, equality, relational, conditional, type coercion, default
* if, else if, else
* functions [DW Examples](https://docs.mulesoft.com/mule-runtime/4.3/dataweave-cookbook)
* string literals for output e.g. ```Message: #[payload]``` or ```#['\nMessage: ' ++ payload]``` or ```[upper('Goodbye') ++ ' ' ++ attributes.queryParams.fullName as String]```

## Variables
* ```Set Variable``` e.g. ``` Name:firstName Value:#[message.atrributes.queryParams.name]```

then reference ```vars.firstName``` in GET/hello HTTP listener response.



