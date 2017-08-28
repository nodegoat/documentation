### Query

To query the nodegoat API you need a valid domain, a valid path, and a valid query component. The following URL contains the possible basic domain, path, and query parameters:

**Authenticated, access Project 1, access Project’s data, Type 2, apply Scope 3, apply Filter 4, request Object 5 & 6 & 7, request Object 8, quick search for 'A', apply a JSON-formatted filter form:**

GET https://nodegoat.io/project/1/data/type/2/scope/3/filter/4/object/5,6,7?object_id=8&search=A&form={}

**Authenticated, access Project 1, access Project’s data Model, request Types 2 & 3 & 4**

GET https://nodegoat.io/project/1/model/type/2,3,4

#### Domain

The domain indicates whether you are creating an authenticated or unauthenticated/open request.

**Authenticated**

When making an authenticated request, HTTPS is required and should query nodegoat’s main API domain at **nodegoat.io** or **api.nodegoat.net**.

**Unauthenticated**

To make an unauthenticated request, you use the subdomain of your nodegoat Domain’s to query the nodegoat API over unencrypted HTTP at **DOMAIN.nodegoat.io** or **api.DOMAIN.nodegoat.net**. When you have an institutional installation of nodegoat you use the main API domain, you also have the option to use HTTPS.

#### Path

The path tells the API what Project and what data you want to access.

##### //nodegoat/A

Specify which nodegoat Project to access. __Optional__.

| A | Description |
| -- | -- |
| __/ project / *ID*__ | Access a specific nodegoat Project. If this is left out, the default configured Project is assumed. |

##### //nodegoat/A/B

Specify the mode. One of the following parameters has to be provided.

| B | Description |
| -- | -- |
| __/ *ID*__ or __?id = *ID*__ | Directly access Objects with their corresponding nodegoat IDs or other identifiers (see [data Model](/configuration/data_model/README.md) on how to indicate what Object Descriptions can be used for identification). The ID can also be provided using the query component *id* (both GET and POST). The query component has to be used when identifiers contain characters reserved for URLs. |
| __/ data__ | Access the Project’s data. |
| __/ model__ | Access the Projects's data Model. |

##### //nodegoat/A/B:data/C

Specify for which Type you want to access the data.

| C | Description |
| -- | -- |
| __/ type / *ID*__ | Access data for the specified Type. |

##### //nodegoat/A/B:data/C/D

Apply Project- and Type-specific operations to the request. More than one of the following parameters can be provided. __Optional__.

| D | Description |
| -- | -- |
| __/ scope / *ID*__ | Apply the specified scope to the request. This allows you to generate highly-relational and ready-to-use data structures using nodegoat Scope functionality. |
| __/ filter / *ID*__ | Apply the specified filter to the request. Additionally, the filter can be manipulated in the query component of the request. |
| __/ object / *ID*(,*ID*)__ | Select the specified Object(s). |

##### //nodegoat/A/B:model/C

Specify for which Type(s) to access the data Model.

| C | Description |
| -- | -- |
| __/ type / *ID*(,*ID*)__ | Access the data Model for the specified Type(s). |

#### Component

The query component allows you to further specify your request by means of search parameters. It is also possible to POST the query component instead of using GET (e.g. when creating large requests that exceed the GET limit).

##### //nodegoat/A/B:data/C/D?Q

All parameters in the query component are optional. When combined, each additional parameter will filter the result (AND).

Query the API for a Type's data Model to get an overview of the possible IDs for Object Descriptions, Sub-Object Details, and Sub-Object Descriptions.

| Q | Description |
| -- | -- |
| __object_id = *ID*(,*ID*)__ | Select the specified Object(s). |
| __search = *value*__ | Quick search Objects for 'value'. |
| __filter = *ID*__ or __*value*__ | Apply a JSON-formatted [filter](/usage/filter/README.md). The filter parameter allows you to customise and apply full-featured nodegoat filters to your query. |
| __scope = *ID*__ or __*value*__ | Apply a JSON-formatted [filter](/usage/scope/README.md). The scope parameter allows you to customise and apply full-featured nodegoat scopes to your query. |
| __output = *output*__ | Specifiy the output format: 'raw' for native and fast output of the data without additional processing such as parsing Object names, or 'default'. |
| __limit = *nr*__ | Limit the results to a maximum amount of Objects. Handy for pagination purposes. |
| __offset = *nr*__ | Offset the results with a specific amount of Objects. Handy for pagination purposes. |

##### //nodegoat/A/B:model/C?Q

All parameters in the query component are optional.

| Q | Description |
| -- | -- |
| __output = *output*__ | Specifiy the output format: 'template' for relational name-based IDs instead of numeric IDs (easy for storage puposes, see [store Model](/usage/API/store.md#model)), or 'default'. |

#### Response

The result from your request to the nodegoat API can be found in the JSON response under the key 'data'. The result is a JSON dictionary that promotes direct lookup and access to its structure.

The specific response depends on the mode (model or data, see the [previous Query section](/usage/API/query.md)) of your request.

##### Model

In mode = model the result contains the requested Type IDs with the Type's configuration.

##### Data

In mode = data the result contains the requested or queried Object IDs with the Object's definition.
