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

The path tells the API what Project and data you want to access. The following parameters provide the API with project specific, and subsequently with data or Data Design specific request information.

##### ://nodegoat/A

| A | Description |
| -- | -- |
| __/ project / *ID*__ | Optional. Access a specific nodegoat Project. If this is left out, the default configured Project is assumed. |
| __/ data or / design__ | Specify the mode. Access the Project’s data or Data Design. |

##### ://nodegoat/A/data/B

| B | Description |
| -- | -- |
| __/ type / *ID*__ | Access the specified Type. |
| __/ scope / *ID*__ | Optional. Apply the specified scope to the request. This allows you to generate highly-relational and ready-to-use data structures using nodegoat Scope functionality. |
| __/ filter / *ID*__ | Optional. Apply the specified filter to the request. Additionally, the filter can be manipulated in the query component of the request. |
| __/ object / *ID*(,*ID*)__ | Optional. Select the specified Object(s). |

##### ://nodegoat/A/design/B

| B | Description |
| -- | -- |
| __/ type / *ID*(,*ID*)__ | Request the specified Type(s). |

#### Query component

The query component allows you to further specify your request by means of search parameters. It is also possible to POST the query component instead of using GET (e.g. when creating large requests that exceed the GET limit).

##### ://nodegoat/A/data/B?C

All parameters in the query component are optional. When combined, each additional parameter will filter the result (AND).

Query the API for a Type's Data Design to get an overview of the possible IDs for Object Descriptions, Sub-Object Details, and Sub-Object Descriptions.

| C | Description |
| -- | -- |
| object_id = *ID*(,*ID*) | Select the specified Object(s). |
| search = *value* | Quick search Objects for 'value'. |
| object_definition[*ID*] = *value* | Query Objects for definitions that contain 'value'. |
| object_sub[*ID*][object_sub_date] = *value* | Query Objects for Sub-Objects that fall within the date specified by 'value'. |
| object_sub[*ID1*][object_sub_definition][*ID2*] = *value* | Query Objects for Sub-Objects for definitions that contain 'value'. |
| filter[*target*] = *value* | When a Filter is applied in the query path, the filter parameter allows you to target and change the configuration of the Filter before the Filter is applied. |

##### ://nodegoat/A/design/B?C

Design currently does not have an additional query component.