## Data Entry
Once you have a Project and Data Design running, you can enter data in the Data module. Here you create new Objects in a Type or new Categories in a Classification. nodegoat follows your custom Data Design and will use the names of the Types and Classifications you have created throughout the interface. This means that you will never encounter a button like 'Create new Object in Type'. Rather, buttons will contain the name of the Type or Classification as specified in the Data Design. If you have created a Type called 'Letter' you will be able to navigate to this Type in the Data module and click 'Add Letter' to create a new Object in this Type.

### Add / Edit / Delete an Object or Category
To add an Object or Category, click 'Add [*name of Type/Classification*]'.

To edit an Object or Category, click 'edit' at the relevant Object or Category.

To delete an Object or Category, click 'del' at the relevant Object or Category.

When you add a new Object or edit an existing Object, you spicify the name of the Object, a number of Object Descriptions, and a number of Sub-Objects. Whether you use a fixed field for the name of an Object, the number of Object Descriptions, and Sub-Objects is configured in the [Data Design](../../configuration/data_design/README.md) module.

When you add a new Category or edit an existing Category, you spicify the name of the Category, and number of Category Descriptions. Whether you use a fixed field for the name of a Category and the number of Category Descriptions is configured in the [Data Design](../../configuration/data_design/README.md) module.

### Name
A single line input field. Enter a single line string (max 5000 characters). The name of an Object or Category stores unformatted characters.

### Object Descriptions and Category Descriptions

#### String
A single line input field. Enter a single line string (max 5000 characters). A string stores unformatted characters.

#### Type
This Object Description is a search box with wich you can query the referenced Type. One Object Description can contain multiple relations to the referenced Type.

#### Classification
This Object Description is a search box with wich you can query the referenced Classification. One Object Description can contain multiple relations to one Classification.

#### Reversed Classification
A relation to a Reversed Classification, not editable.

#### Integer
An integer. Whole number, no decimals (max 11 digits)

#### Text
A multi-line input field. Enter non-formatted text (max 65535 characters).

#### Text (layout)
A multi-line input field. Enter formatted text (max 65535 characters).

#### Text (tags & layout)
A multi-line input field. Enter formatted text (max 65535 characters). In this Object Description, words can be related to other Objects. To create a textual relation, select a word and click the green 'object' button that appears. Select a Type and find one or more Objects. To edit a textual relation, click on the relationship and click the blue 'object' button. Click the blue '&' button to re-use a previously used relation. Click the blue '+' button to select the last used relation. Click the red 'x' button to remove an existing relation.

#### True/False
A true/false field.

#### Date
A date field, using the following date formats:
<ul><li>y (1687)</li><li>-y (-800)</li><li> m-y (03-1687 / 3-1687)</li><li>m--y (03--800 / 3--800)</li><li>-m-y (-03-800 / -3-800)</li><li>d-m-y (09-03-1687 / 9-3-1687)</li><li> d-m--y (09-03--800 / 9-3--800)</li><li>-d-m-y (-09-03-800 / -9-3-800</li></ul>

#### Media
Upload any kind of media (i.e. png, pdf, mp3).

#### Media (External)
Link to external media resources (e.g. http://url.com/map.png or http://youtu.be/jm1os4VzTgA)

#### External
An external relation using URIs. URIs can be plain URLs, or can be retrieved by connecting to the nodegoat Linked Data module to dynamically query SPARQL/API resources like VIAF or Wikipedia

### Sub-Objects
In case a Type is configured to contain Sub-Objects, the Editor for Sub-Objects will appear. Unique Sub-Objects can be added by clicking the '+' button. Non-unique Sub-Objects can be added by clicking the '+' button or the '+\+' button. The '+\+' button will open a popup that allows you to predefine multiple Sub-Objects.

#### Sub-Object Dating
Based on the settings of the Sub-Object, you can either specify a period by means of Date Start and Date End or a single Date. The formats as specified for the [Date Object Description](#date) are available. When a period can be specified, a checkbox is available to enable ongoing periods ("Infinite / no ending date"). If the date is taken from another source, the date is not editable.

#### Sub-Object Location
Based on the settings of the Sub-Object, you can select a Reference or Point for the location of the Sub-Object (the Area option is not available yet). When you select 'Reference' you can select a Type and Sub-Object. If one or more of these options are locked, the locked options can not be selected. When you select 'Point' you can either enter a latitude and longitude value or click on the green 'map' button to select a point on a map. If the location is taken from another source, the location is not editable.

#### Sub-Object Descriptions
Based on the settings of the Sub-Object, Sub-Object Descriptions can be added. These have the same options as the [Object Descriptions](#object_descriptions_and_category_descriptions). Relational Sub-Object Descriptions can contain only one relation.

### Save an Object or Category
Click 'Save [*name of Type/Classification*]' to save an Object or Category.
