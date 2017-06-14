### Store

To store data through the nodegoat API you need a valid domain, a valid path, and use user authentication. The data you submit has to be formatted in JSON. Storing data in nodegoat will start a new [transaction](https://en.wikipedia.org/wiki/Database_transaction): the transaction will be commited when all data is successfully processed, or rolled back when an error occurs.

The following URL contains the possible basic domain and path parameters:

**Access Project 1, access Project’s data, Type 2, target Object 3, overwrite the Object with the provided JSON-formatted Object data**

PUT https://nodegoat.io/project/1/data/type/2/object/3 '{"object": {"object_name_plain": "A Node in nodegoat"},"object_definitions": {"1": {"object_description_id": 1,"object_definition_ref_object_id": null,"object_definition_value": "Hello"}}}'

#### Domain

Since you are making an authenticated request, HTTPS is required and should query nodegoat’s main API domain at **nodegoat.io** or **api.nodegoat.net**.

#### Path

The path tells the API what Project and what data you want to target.

##### //nodegoat/A

Specify which nodegoat Project to access. __Optional__.

| A | Description |
| -- | -- |
| __/ project / *ID*__ | Access a specific nodegoat Project. If this is left out, the default configured Project is assumed. |

##### //nodegoat/A/B

Specify the mode.

| B | Description |
| -- | -- |
| __/ data__ | Access the Project’s data. |

##### //nodegoat/A/B:data/C

Specify for which Type you want to change the data.

| C | Description |
| -- | -- |
| __/ type / *ID*__ | Access data for the specified Type. |

##### //nodegoat/A/B:data/C/D

Apply Project- and Type-specific operations to the request. You can either target an object in the path, or specify it in the data you submit. __Optional__.

| D | Description |
| -- | -- |
| __/ object / *ID*__ | Target the specified Object. |

#### Method

The request method allows you to specify the operation you want to perform. Each method allows you to submit nodegoat Object dictionaries that are structured using the [Query Design response](/usage/API/query.md#design) and formatted following the [Query Data response](/usage/API/query.md#data):

```json
OBJECT = {
    "object": {
        "object_name_plain": "A Node in nodegoat",
    },
    "object_definitions": [
        {
            "object_description_id": 1,
            "object_definition_ref_object_id": null,
            "object_definition_value": "Hello"
        }
    ],
    "object_subs": [
        {
            "object_sub": {
                "object_sub_id": null,
                "object_sub_details_id": 3,
                "object_sub_date_start": 17680101,
                "object_sub_date_end": 17680101,
                "object_sub_location_ref_object_id": 4,
                "object_sub_location_ref_type_id": 5,
                "object_sub_location_ref_object_sub_details_id": 6,
                "object_sub_location_type": "reference",
            },
            "object_sub_definitions": [
                {
                    "object_sub_description_id": 7,
                    "object_sub_definition_ref_object_id": null,
                    "object_sub_definition_value": "Great Place"
                }
            ]
        }
    ]
}
```

##### PUT

When submitting data with the PUT method, you can overwrite the Object specified in the path, overwrite the Objects specified in the submitted data, or create new Objects.

To overwrite an Object specified in the path 'https://nodegoat.io/project/1/data/type/2/object/3', you submit a single Object dictionary:

```json
OBJECT
```

To overwrite Objects specified in the submitted data, you access the path without an Object ID 'https://nodegoat.io/project/1/data/type/2/object/', create the key 'update', and provide a dictionary with Object IDs as keys and Object dictionaries as values:

```json
{
    "update": {
		"3": OBJECT,
		"333": ...
	}
}
```

To add new Objects to a Type, you access the path without an Object ID 'https://nodegoat.io/project/1/data/type/2/object/', create the key 'add', and submit a list with Object dictionaries:

```json
{
    "add": [
		OBJECT,
		...
	]
}
```

To both add and update Objects in a single request, you access the path without an Object ID 'https://nodegoat.io/project/1/data/type/2/object/' and provide the key 'add' with a list and the key 'update' with a dictionary:

```json
{
    "add": [OBJECT, ...],
    "update": {"3": OBJECT, "333": ...}
}
```


##### PATCH

When submitting data with the PATCH method, you can update the Object specified in the path or update the Objects specified in the data. Any Object Description/Sub-Object/Sub-Object Description that is not specified in the submitted data will not be touched. For instance, this allows you to update specific Object Descriptions and append new Sub-Objects.

To update an Object specified in the path 'https://nodegoat.io/project/1/data/type/2/object/3', you submit a single Object dictionary that only contains the data you want to update:

```json
OBJECT
```

To update Objects specified in the submitted data, you access the path without an Object ID 'https://nodegoat.io/project/1/data/type/2/object/' and provide a dictionary with Object IDs as keys and Object dictionaries as values:

```json
{
    "3": OBJECT,
    "333": ...
}
```

##### DELETE

To delete Objects, you either apply the method DELETE to the path to a specific Object, e.g. 'https://nodegoat.io/project/1/data/type/2/object/3', or you access the path without an Object ID and submit a dictionary with the Object IDs as keys:

```json
{
	"3": true,
	"333": true
}
```

#### Response

The result from your submission to the nodegoat API can be found in the JSON response under the key 'data'. A list will be returned with the Object IDs that have been 'added', 'updated', or 'deleted'.

