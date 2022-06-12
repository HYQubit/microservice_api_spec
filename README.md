# Microservice Api Spec

The Huayi Microservice API is organized around [REST](http://en.wikipedia.org/wiki/Representational_State_Transfer). Our API has predictable resource-oriented URLs, returns [JSON-encoded](http://www.json.org/) responses, and uses standard HTTP response codes, authentication, and verbs.

## Errors

We uses conventional HTTP response codes to indicate the success or failure of an API request. In general: Codes in the `2xx` range indicate success. Codes in the `4xx` range indicate an error that failed given the information provided (e.g., a required parameter was omitted, a commit failed, etc.). Codes in the `5xx` range indicate an error with microservice's servers (these are rare).

| Status code                        | Description                                                  |
| ---------------------------------- | ------------------------------------------------------------ |
| 200 - OK                           | Everything worked as expected.                               |
| 400 - Bad Request                  | The request was unacceptable, often due to missing a required parameter. |
| 401 - Unauthorized                 | No valid API key provided.                                   |
| 402 - Request Failed               | The parameters were valid but the request failed.            |
| 403 - Forbidden                    | The API key doesn't have permissions to perform the request. |
| 404 - Not Found                    | The requested resource doesn't exist.                        |
| 409 - Conflict                     | The request conflicts with another request (perhaps due to using the same idempotent key). |
| 429 - Too Many Requests            | Too many requests hit the API too quickly. We recommend an exponential backoff of your requests. |
| 500, 502, 503, 504 - Server Errors | Something went wrong on Stripe's end. (These are rare.)      |


### Attributes

**type** `string`

The type of error returned.

**code** `string`

For some errors that could be handled programmatically, a short string indicating the error code reported.

**message** `string`

A human-readable message providing more details about the error. For card errors, these messages can be shown to your users.

**param** `string`
If the error is parameter-specific, the parameter related to the error. For example, you can use this to display a message near the correct form field.
