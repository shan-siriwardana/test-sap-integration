# API Contracts Overview
 
Below is a summary of service contracts of APIs.  

Detailed YAML files describing the service contracts along with sample requests/responses can be found in the [API Service Contracts](https://github.com/shan-siriwardana/test-sap-integration/tree/main/API%20service%20contracts) folder. These yaml files can be opened at 'https://editor.swagger.io'.



| API          | Operation          | URI                             |
|--------------|--------------------|---------------------------------|
| Basket API   | Create Basket      | `POST /baskets`                 |
| Basket API   | Add Items          | `POST /baskets/{basketId}/items`|
| Basket API   | Start Checkout     | `POST /baskets/{basketId}/sessions` |
| Basket API   | Get Checkout Session | `GET /checkout-sessions/{id}`  |
| Payment API  | Authorize Payment  | `POST /payments/confirm`        |
| Payment API  | Capture Payment    | `POST /payments/{authId}/capture` |
| Order API    | Create Order       | `POST /orders`                  |
| Checkout API | Confirm Checkout   | `POST /checkout/confirm`        |