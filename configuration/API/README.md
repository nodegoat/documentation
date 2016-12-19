## API

The API configuration module allows you to select and configure the Projects that can be accessed through the API and the Users that can access the API. The API uses the Projects present in the nodegoat Domain for access to the data model and configurations such as Filters and Scopes. Additionally the Users that have access to these Projects can be used to provide optional authentication to be allowed access the Projects through the API.

### Projects

In the API configuration module you select the Projects that can be accessed externally through the API. After saving the selection, there are specific configuration parameters for each selected Project.
*    Indicate whether the Project is the default Project that can be accessed through the API. This allows you to leave out the Project ID [path parameter](/usage/API/query.md#path) when querying the API.
*    Require authentication to access the Project through the API.

### Authentication

A request to the API requires authentication credentials of a valid User when a client tries to access a Project that requires it. The authentication procedure follows the OAuth 2.0 protocol. To allow clients access to your Project you first need to add the client to the configuration of the API. Subsequently you assign Users to the client that provide the necessary authentication for access to your Projects.

#### Client

A client serves to identify the external requests made to your nodegoat Domain.

To add a client:
*    Specify whether the client is allowed access (active or inactive). You can change this state by editing the client.
*    Enter the name/identity of the client.
*    Provide the default validity period Users assigned to the client are allowed access to the API through the client. Leave the validity period empty to set the default period to allow for indefinite access. You can change the default validity period by editing the client.

Currently clients can not make authorisation requests on behalf of nodegoat Users. You have to manually assign Users to the client to be able to gain access to your Projects.

_In the future clients will be able to request authorisation for nodegoat Users. The required client identifiers and passkeys (secret) are generated automatically. The passkey can be regenerated when the passkey of the client has been compromised._

#### User

Users are assigned to clients to provide the necessary authentication when a client accesses the API. The provided User identity configures nodegoat just like a regular nodegoat login would. Important configurations based on the User’s identity are:
*    Whether the User has access to the requested Project.
*    Whether the User has the required view and edit clearances to view the data.

To assign a User to a client, click 'add' at the relevant client, and:
*    Specify whether the client is allowed access (active or inactive) through the client. You can change this state by editing the User assignment.
*    Search and select the relevant User.
*    Provide the validity period the User is allowed access to the API through the client. Leave the validity period empty to allow for indefinite access. You can change the validity period by editing the User assignment.

The required passkey (token) is generated automatically. Consult the [API usage section](/usage/API/README.md) to start making authenticated requests through the client with the generated User passkey (token).
