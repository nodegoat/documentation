### Type

Types contain Objects. Objects are things. In the data Model module you model the structure of your Types. This structure describes the Objects in a Type. Objects are described by Object Descriptions, Sub-Objects, and Sub-Object Descriptions.

To add a Type, click 'Add Type'.

To edit an existing Type, click the blue 'edit' button at the relevant Type.

To empty an existing Type, click the red 'empty' button at the relevant Type. This will remove all the Objects in this Type while leaving the Model of this Type intact.

To delete an existing Type, click the red 'del' button at the relevant Type. This will remove both the Objects in this Type plus the Model of this Type.

#### Add / Edit a Type

Specify the name of the Type. This name is used throughout nodegoat to identify this Type.

You can specify a color for the Type. This color is the default color of the Type and will be used for coloring in visualisations and highlights when no other color has been specified in the [Project](/configuration/project/README.md#organise) or [Conditions](/usage/conditions/README.md).

Specify [Conditions](/usage/conditions/README.md) that are used for a Type.

Specify one or more definitions that describe a type. These definitions are exposed via the [API](/configuration/API/README.md).

##### Object

Click the tab 'Object' to configure the name of Objects as well as Object Descriptions.

###### Object Name

Check the 'Fixed Field' checkbox to enable a static name field for each Object in this Type. If the static name field is disabled, at least one Object Description has to be used for the name of the Object.

Check the 'In Overviews' checkbox to show this name in the overviews.

###### Object Descriptions

*Intrinsic/static attributes of an Object are described by Object Descriptions.*

Click 'add' to create new Object Descriptions.

Give an Object Description a name by entering a name.

Select the kind of data that will be stored in the Object Description:

| Name | Description | Limit |
| -- | -- | -- |
| String | A single line string. | 5000 characters |
| Type | A relation to another Object in the same or a different Type. One Object Description can contain multiple relations to the referenced Type. | N/A |
| Classification |  A relation to a Category in a Classification. One Object Description can contain multiple relations to one Classification. | N/A |
| Reversed Classification |  A relation to a Reversed Classification. | N/A |
| Integer | An integer (whole number, no decimals). | 11 digits |
| Text | Non-formatted text field. | 65535 characters |
| Text (layout) | Formatted text field. | 65535 characters |
| Text (Tags & layout) | Formatted text field. In this Object Description, words can be related to other Objects | 65535 characters |
| True/False | A true/false field. | N/A |
| Date | A date field, using the following date formats:<ul><li>y (1687)</li><li>-y (-800)</li><li> m-y (03-1687 / 3-1687)</li><li>m--y (03--800 / 3--800)</li><li>-m-y (-03-800 / -3-800)</li><li>d-m-y (09-03-1687 / 9-3-1687)</li><li> d-m--y (09-03--800 / 9-3--800)</li><li>-d-m-y (-09-03-800 / -9-3-800</li></ul> | N/A |
| Media | Upload any kind of media (i.e. png, pdf, mp3). | N/A |
| Media (External) | Link to external media resources (e.g. http://url.com/map.png or http://youtu.be/jm1os4VzTgA). | N/A |
| External | An external relation using URIs. URIs can be plain URLs, or can be retrieved by connecting to the nodegoat Linked Data module to dynamically query SPARQL/API resources like VIAF or Wikidata. | N/A |

Per Object Description you can check or uncheck six checkboxes to specify how the Object Description will be used.

1. Check the first checkbox 'Possibility for multiple Definitions for this Description' to allow multiple values to be stored in an Object Description. This option is only available for relational Object Descriptions (Type, Classification)

2. Check the second checkbox 'Definitions for this Description are unique' to allow only unique values to be stored in an Object Description.

3. Check the third checkbox 'Use Description for names' to use the value or values stored in an Object Description as the name or part of the name of the Object. If the static name field is disabled, this option has to be set at least once. If not, nodegoat will not be able to generate a name for the Object.

4. Check the fourth checkbox 'Use Description for quick search' to allow an Object Description to be searched via the Quick Search functionality.

5. Check the fifth checkbox 'Show Description in overviews' to show the value or values stored in an Object Description as a column in overviews of Objects in this Type.

6. Check the sixth checkbox 'Use the Description for Object identification (used in API queries)' to use the value or values in an Object Description as external identifiers.

*Optional*: In a multi-user Domain: Select the minimum clearance level a user needs to edit an Object Description.

*Optional*: In a multi-user Domain: Select the minimum clearance level a user needs to view an Object Description.

##### Sub-Objects

*Changing/contextualised attributes of an Object are described by Sub-Objects.*

Click the tab 'Sub-Object' to configure the Sub-Objects of a Type.

Click 'add' to create new Sub-Object.

Give a Sub-Object a name by entering a name.

Specify whether a Sub-Object may occur only once per Object by selecting 'Unique'.

Specify whether a Sub-Object is required for every Object by selecting 'Required'.

Specify whether the temporality of a Sub-Object is defined by a date or a period.

*Optional*: In a multi-user Domain: Select the minimum clearance level a user needs to edit the temporality of a Sub-Object.

*Optional*: In a multi-user Domain: Select the minimum clearance level a user needs to view the temporality of a Sub-Object.

*Optional*: Select the source of the date of a Sub-Object.

*Optional*: Check the checkbox 'lock' to only allow for Location References in a Sub-Object.

*Optional*: Select which Type will be the default Type for the Location Reference of a Sub-Object. 

*Optional*: Check the checkbox 'lock' to lock the selected Type for the Location References in a Sub-Object.

*Optional*: Select which Sub-Object of the selected Type will be the default Sub-Object for the Location Reference of a Sub-Object. 

*Optional*: Check the checkbox 'lock' to lock the selected Sub-Object for the Location References in a Sub-Object.

*Optional*: Select the source of the Location Reference of a Sub-Object.

*Optional*: In a multi-user Domain: Select the minimum clearance level a user needs to edit the Location Reference of a Sub-Object.

*Optional*: In a multi-user Domain: Select the minimum clearance level a user needs to view the Location Reference of a Sub-Object.

##### Sub-Object Descriptions

Click 'add' to create new Sub-Object Descriptions.

Give a Sub-Object Description a name by entering a name.

The same kinds of data can be selected for a Sub-Object Description as for an [Object Description](#object-descriptions).

*Optional*: In a multi-user Domain: Select the minimum clearance level a user needs to edit a Sub-Object Description.

*Optional*: In a multi-user Domain: Select the minimum clearance level a user needs to view a Sub-Object Description.
