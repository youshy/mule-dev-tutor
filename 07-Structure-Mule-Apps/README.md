# Structure

## See hello.jar for example extended from WTs to show Flow reference  vs. VM connector vs. Request

* Multiple flows - sub flows, private flows
    * subflows inherit parent flow error handling and are executed as though processor is in calling flow
    * flow with no event source is 'private flow'
    * flow references link calling flow to subflow are __synchronous__
    * content of event persists through flows, unless crosses transport boundary i.e. when new HTTP listener request triggered a new event is created. Hello flow called Goodbye flow and Payload / attributes in calling event (Hello) were replaced with HTTP response payload (Goodbye) / attributes.queryParams.

* Pass events using asynchronous queues - VM connector implements simple queueing
    * parallelism 
    * communicate with another application in same Mule domain
    * distribute work across cluster
        * Transient queues store data in memory - faster but lose data in event of crash
        * Persistent - slower but more reliable

* Structure
  * global.xml - global configuration items
  * interface.xml - e.g. APIKit router, APIKit errors and global error handler
  * implementation.xml - application specific routes
  * properties config ```/apdev-examples/src/main/resources/config.yaml```
  * application metadata ```

* Metadata
 * generally datasense can pick up metadata
 * Transform message component has manual input 
    * Set Metadata
* Metadata tab in properties view of event processors
* Mule -> Manage Metadata Types
    * ```/wt9-3_apdev-flights-ws_solution/src/main/resources/application-types.xml```
    Stores all manually created metadata conditions.

