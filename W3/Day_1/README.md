#### Idempotence:
From a RESTful service standpoint, for an operation (or service call) to be idempotent, clients can make that same call 
repeatedly while producing the same result. In other words, making multiple identical requests has the same effect as making
a single request. Note that while idempotent operations produce the same result on the server (no side effects), the response
itself may not be the same (e.g. a resource's state may change between requests).<br/>
**PUT** and **DELETE** are designed to be idempotence<br/>

*body-parse* is a small js library that can help us to convert the body into something that we can work with <br/>
