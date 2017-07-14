## Objects

Since most of the buttons in the interface of nodegoat are based on labels that are defined in a custom Data Design, we will use an example. 

### Add / Edit / Delete an Object

To add an Object, click 'Add [*name of Type*]'.

To edit an Object, click 'edit' at the relevant Object.

To delete an Object, click 'del' at the relevant Object.

When you add a new Object or edit an existing Object, you spicify the name of the Object, a number of Object Descriptions and a number of Sub-Objects. Whether you use a fixed field for the name of an Object and the number of Object Descriptions and Sub-Objects is configured in the [Data Design](configuration/data_design/README.md) module.

### Name
A single line input field. Enter a single line string (max 5000 characters). The name of an Object stores unformatted characters.

### Object Descriptions

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
A multi-line input field. Enter formatted text. In this Object Description, words can be related to other Objects (max 65535 characters).

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

### Sub-Object Descriptions

### Save an Object

Click 'Save Person' to save an Object.