### Store

To store data through the nodegoat API you need a valid domain, a valid path, and use user authentication. The data you submit has to be formatted in JSON. Storing data in nodegoat will start a new [transaction](https://en.wikipedia.org/wiki/Database_transaction): the transaction will be commited when all data is successfully processed, or rolled back when an error occurs.

**Example:** The following URL contains the possible basic domain and path parameters to store data to an Object:

**Access Project 1, access Project’s data, Type 2, target Object 3, overwrite the Object with the provided JSON-formatted Object data**

PUT https://nodegoat.io/project/1/data/type/2/object/3 '{"object": {"object_name_plain": "A Node in nodegoat"},"object_definitions": {"1": {"object_description_id": 1,"object_definition_ref_object_id": null,"object_definition_value": "Hello"}}}'

#### Domain

Since you are making an authenticated request, HTTPS is required and should query nodegoat’s main API domain at **nodegoat.io** or **api.nodegoat.net**.

#### Path

The path tells the API what mode and data you want to target, either Object data or Type templates.

##### //nodegoat/A

Specify which nodegoat Project to access. __Optional__.

Only applicable when storing data to Objects: 'mode = data', see the [next section '//nodegoat/A/B'](/usage/API/store.md#nodegoatAB)).

Since the data Model transcends the Projects within a nodegoat Domain, no project should be specified when storing data to the data Model ('mode = model'). The user has to have administrator clearance to be be able change the data Model.

| A | Description |
| -- | -- |
| __/ project / *ID*__ | 'mode = data' only. Access a specific nodegoat Project. If this is left out, the default configured Project is assumed. |

##### //nodegoat/A/B

Specify the mode.

| B | Description |
| -- | -- |
| __/ data__ | Access the Project’s data. |
| __/ model__ | Access the Projects's data Model. Requires administrator clearance. |

##### //nodegoat/A/B:data/C

Specify for which Type you want to change the data.

| C | Description |
| -- | -- |
| __/ type / *ID*__ | Access data for the specified Type. |

##### //nodegoat/A/B:data/C/D

Apply Project- and Type-specific operations to the request. You can either target an Object in the path, or specify it in the data you submit. __Optional__.

| D | Description |
| -- | -- |
| __/ object / *ID*__ | Target the specified Object. |

##### //nodegoat/A/B:model/C

Specify for which Type you want to change the template. You can either target a Type in the path, or specify it in the data you submit. __Optional__.

| C | Description |
| -- | -- |
| __/ type / *ID*__ | Access data for the specified Type. |

#### Method

The request method allows you to specify the operation you want to perform for either Object data in data mode or Type templates in data Model mode.

##### Data

Each method allows you to submit nodegoat Object dictionaries that are structured using the [Query Model response](/usage/API/query.md#model) and formatted following the [Query Data response](/usage/API/query.md#data):

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

###### PUT

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

###### PATCH

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

###### DELETE

To delete Objects, you either apply the method DELETE to the path to a specific Object, e.g. 'https://nodegoat.io/project/1/data/type/2/object/3', or you access the path without an Object ID and submit a dictionary with the Object IDs as keys:

```json
{
	"3": true,
	"333": true
}
```

##### Model

Each method allows you to submit nodegoat Type template dictionaries that are formatted following the [Query Model response](/usage/API/query.md#model). nodegoat Type templates can be dynamic: it is possible to use names as IDs instead of the numeric IDs within Type templates (e.g. whenever the template references other Type templates like 'object_description_ref_type_id' or 'object_sub_details_location_ref_object_sub_details_id'), see the output of [output 'template'](usage/API/query.md#nodegoatABmodelCQ). By using name IDs instead of numeric IDs, you are able to store a whole nodegoat data Model in one go. 

```json
TYPE = {
	"type": {
		"id": "Person",
		"is_classification": false,
		"is_reversed_classification": false,
		"name": "Person",
		"color": "#ff00ff",
		"use_object_name": false,
		"object_name_in_overview": true
	},
	"object_descriptions": [
		{
			"object_description_id": "Second Name",
			"object_description_name": "Second Name",
			"object_description_value_type": "",
			"object_description_value_type_options": "",
			"object_description_is_unique": false,
			"object_description_is_identifier": false,
			"object_description_ref_is_multi": false,
			"object_description_ref_type_id": false,
			"object_description_in_name": true,
			"object_description_in_search": true,
			"object_description_in_overview": true,
			"object_description_clearance_view": 0,
			"object_description_clearance_edit": 0
		}
	],
	"object_sub_details": [
		{
			"object_sub_details": {
				"object_sub_details_id": "Birth",
				"object_sub_details_name": "Birth",
				"object_sub_details_is_unique": true,
				"object_sub_details_required": true,
				"object_sub_details_is_date_range": false,
				"object_sub_details_date_use_object_sub_details_id": false,
				"object_sub_details_date_use_object_sub_description_id": false,
				"object_sub_details_date_use_object_description_id": false,
				"object_sub_details_location_ref_only": false,
				"object_sub_details_location_ref_type_id": "City",
				"object_sub_details_location_ref_type_id_locked": false,
				"object_sub_details_location_ref_object_sub_details_id": "Located",
				"object_sub_details_location_ref_object_sub_details_id_locked": false,
				"object_sub_details_location_use_object_sub_details_id": false,
				"object_sub_details_location_use_object_sub_description_id": false,
				"object_sub_details_location_use_object_description_id": false,
				"object_sub_details_location_use_object_id": false,
				"object_sub_details_clearance_view": 0,
				"object_sub_details_clearance_edit": 0
			},
			"object_sub_descriptions": [
				{
					"object_sub_description_id": "Notes",
					"object_sub_description_name": "Notes",
					"object_sub_description_value_type": "text_tags",
					"object_sub_description_value_type_options": "",
					"object_sub_description_ref_type_id": false,
					"object_sub_description_use_object_description_id": false,
					"object_sub_description_in_overview": true,
					"object_sub_description_clearance_view": 4,
					"object_sub_description_clearance_edit": 4
				}
			]
		}
	]
}
```

###### PUT

When submitting Type templates with the PUT method, you can overwrite the Type specified in the path, overwrite the Types specified in the submitted data, or create new Types.

To overwrite a Type specified in the path 'https://nodegoat.io/model/type/1/', you submit a single Type template dictionary:

```json
TYPE
```

To overwrite Types specified in the submitted data, you access the path without a Type ID 'https://nodegoat.io/model/type/', create the key 'update', and provide a dictionary with Type IDs (or Type names) as keys and Type template dictionaries as values:

```json
{
    "update": {
		"Person": TYPE,
		"3": ...
	}
}
```

To add new Types, you access the path without a Type ID 'https://nodegoat.io/model/type/', create the key 'add', and submit a list with Type template dictionaries:

```json
{
    "add": [
		TYPE,
		...
	]
}
```

To both add and update Types in a single request, you access the path without a Type ID 'https://nodegoat.io/model/type/' and provide the key 'add' with a list and the key 'update' with a dictionary:

```json
{
    "add": [TYPE, ...],
    "update": {"Person": TYPE, "3": ...}
}
```

###### PATCH

When submitting data with the PATCH method, you can update the Type specified in the path or update the Types specified in the data. Any Object Description/Sub-Object/Sub-Object Description that is not specified in the submitted data will not be touched. For instance, this allows you to create or change specific Object Descriptions and configure new Sub-Objects.

To remove a Object Description/Sub-Object/Sub-Object Description from the Type, provide their respective ID (or name as ID), and set their name (e.g. 'object_description_name') to empty or null.

To update a Type specified in the path 'https://nodegoat.io/model/type/1/', you submit a single Type template dictionary that only contains the data you want to update:

```json
TYPE
```

To update Types specified in the submitted data, you access the path without a Type ID 'https://nodegoat.io/model/type/' and provide a dictionary with Type IDs (or Type names) as keys and Type template dictionaries as values:

```json
{
	"Person": TYPE,
	"3": ...
}
```

###### DELETE

To delete Types, you either apply the method DELETE to the path to a specific Type, e.g. 'https://nodegoat.io/model/type/1/', or you access the path without a Type ID and submit a dictionary with the Type IDs (or Type names) as keys:

```json
{
	"Person": true,
	"3": true
}
```

#### Response

The result from your submission to the nodegoat API can be found in the JSON response under the key 'data'. A list will be returned with the Type or Object IDs that have been 'added', 'updated', or 'deleted'.

