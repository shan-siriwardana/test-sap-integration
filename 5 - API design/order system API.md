### API specifications
Detailed request/response schemas and OpenAPI definitions for this API are found in the  
[Order System API contract](../2%20-%20API%20service%20contracts/order%20system%20API.yml).




### API internal design

The Order System API is a thin proxy that exposes order operations to upstream clients.

It delegates actual processing to the Order Microservice.