### API specifications
Detailed request/response schemas and OpenAPI definitions for this API are found in the  
[Payment System API contract](../2%20-%20API%20service%20contracts/payment%20system%20API.yml).




### API internal design

The Payment System API is a thin proxy that exposes payment operations to upstream clients.

It delegates actual processing to the Payment Microservice.