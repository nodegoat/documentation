### Basic principles

*   All responses are encoded as JSON.
*   The nodegoat API is [RESTful](https://en.wikipedia.org/wiki/Representational_state_transfer).
*   The API follows the [OAuth 2.0](https://oauth.net/2/) protocol when authentication is required to access the Projects.
    *   Make sure to always send requests over HTTPS.
    *   Provide authentication tokens as 'bearer' in the request's Authorisation header.
    *   Failure to provide authentication tokens over HTTPS will reset the token. The newly generated token can be accessed through the API configuration module.
*   Error messages and other non-fatal messages can be found in the response's root. Errors are provided in the key 'error', its description in the key 'error_description'. Additional non-fatal messages can be found in the key 'msg' which contains an array of messages with the following keys:
    *   label: identifying code belonging to the message.
    *   description: Human-readable text providing additional information, used to assist the client in understanding the error that occurred.
    *   type: contains a value of 'alert' or 'attention' to indicate the severity of the message.
    *   duration: provides a display duration that can be used by the client application.

#### Rate Limiting

The nodegoat API rate limiting (requested records per amount of time) for the
requests of both authenticated and unauthenticated clients. This measure helps to administer the
performance of the API. Additionally the API implements security measures to ban clients for a
certain amount of time in case of repeated failed authentication attempts or exceedance of the rate
limits.

_The current rate limit is set at 25 requests in a window of 15 minutes originating from one IP._

When you have an institutional installation of nodegoat, the rate limit can be ajusted to support the installation's requirements.

