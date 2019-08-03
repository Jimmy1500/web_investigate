# C++ Web Framework Investigation
C++ (Hodge Podge) Webservice Framework Investigation (End to End)  

## Crow (Webservice Microframework)
[Crow](https://github.com/ipkn/crow.git)

## JSON Parser
[RapidJSON](http://rapidjson.org)

## Database Connection
[Portable Component (POCO C++)](https://pocoproject.org)

## Database:
MySQL

## Observation:
### Crow
seems promising, but:  
1. exhibits significant performance degradation / hanging behavior when natively supported json type object with large content was returned in response  
However, returning the same json as string in response works just fine, should be a bug.
2. Memory leak in web socket implementation on exit observed  

### RapidJSON
Fast and robust, I am pretty happy with it, however, further benchmark against other engine (e.g. POCO::JSON) should be performed in order to draw definitive conclusion.

### POCO::DATA
API well designed and suitable for high performance tasks, I am pretty happy with it, postgres implementation not supported out of box, however, interface provided is clean and can easily suppliment your own implementation

### Databae:
MySQL works okay but is sort of shitty, will need to investigate Postgres
