### Query

To query the nodegoat API you need a valid domain, a valid path, and a valid query component. The following URL contains the possible basic domain, path, and query parameters:

**Authenticated, access Project 1, access Project’s data, Type 2, apply Scope 3, apply Filter 4, request Object 5 & 6 & 7, request Object 8, quick search for 'A', query Object Description 9 for 'B', change the specified filter parameter to 'C':**

https://nodegoat.io/project/1/data/type/2/scope/3/filter/4/object/5,6,7?object_id=8&search=A&object_description[9]=B&filter[a][b]=C

**Authenticated, access Project 1, access Project’s Data Design, request Types 2 & 3 & 4**

https://nodegoat.io/project/1/design/type/2,3,4

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
| __/ *ID*__ or __?id = *ID*__ | Directly access Objects with their corresponding nodegoat IDs or other identifiers (see [Data Design](configuration/data_design/README.md) on how to indicate what Object Descriptions can be used for identification). The ID can also be provided using the query component *id* (i.e. when identifiers contain characters reserved for URLs). |
| __/ data__ | Access the Project’s data. |
| __/ design__ | Access the Projects's Data Design. |

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

##### //nodegoat/A/B:design/C

Specify for which Type(s) to access the Data Design.

| C | Description |
| -- | -- |
| __/ type / *ID*(,*ID*)__ | Access the Data Design for the specified Type(s). |

#### Query component

The query component allows you to further specify your request by means of search parameters. It is also possible to POST the query component instead of using GET (e.g. when creating large requests that exceed the GET limit).

##### //nodegoat/A/B:data/C/D?Q

All parameters in the query component are optional. When combined, each additional parameter will filter the result (AND).

Query the API for a Type's Data Design to get an overview of the possible IDs for Object Descriptions, Sub-Object Details, and Sub-Object Descriptions.

| Q | Description |
| -- | -- |
| __object_id = *ID*(,*ID*)__ | Select the specified Object(s). |
| __search = *value*__ | Quick search Objects for 'value'. |
| __form = *value*__ | Apply a JSON-formatted [filter](/usage/filter/README.md). The form parameter allows you to customise and apply full-featured nodegoat filters to your query. |

##### //nodegoat/A/B:design/C?Q

Design currently does not have an additional query component.
