## Import

### Sources
Use the 'Source' tab to upload a file that contains your data. The source file can be either a CSV file or JSON file. For the creation of UTF-8 encoded CSV files, we recommend using LibreOffice. Make sure the number of column headings match the number of columns used in the file. For creating JSON files easily, [OpenRefine](http://openrefine.org/) can be helpful. Or use xslt to transform your XML files into one of these structures.

To add a source file, click 'Add Source'.

To edit an existing Source, click the blue 'edit' button at the relevant Source.

To delete an existing Source, click the red 'del' button at the relevant Source.

### Import Templates
Use the 'Import Template' tab to create an Import Template that maps the data structure in your Source File to your [Data Model](/configuration/data_model/README.md). 

To add a Import Template, click 'Add Import Template'.

To edit an existing Import Template, click the blue 'edit' button at the relevant Import Template.

To delete an existing Import Template, click the red 'del' button at the relevant Import Template.

Enter a Name for the Import Template.

Enter a Description for the Import Template.

Select a previously uploaded source file to show a row per available column / value. Click the red 'del' button to remove empty rows. Click the green 'add' button to add additional rows. Per row you can specify:

* A splitter that is used to split the data field into multiple values.
* If a splitter has been identified: specify whether this data field contains multiple identical values or select one target position.
* Select a Type to which the data is to be imported.
* Select the 'Object Sources', 'Object Name', 'Description', 'Sub-Object Date Start', 'Sub-Object Date End', 'Sub-Object Location Reference', 'Sub-Object Location Latitude', or 'Sub-Object Location Longitude' to which the data is to be imported. When importing to a relational Description, the import process performs a [quicksearch](/usage/data_view/README.md#quicksearch) in the related Type or Classification, using the data found in the source file.
* Check the first checkbox to use data from this column / value to filter similar Objects. Use this setting to find existing Objects that are to be enriched using this Import Template.
* Check the second checkbox to use data from this column / value to establish a relation via a pre-existing nodegoat object ID.
* Check the third checkbox to use data from this column / value to establish a relation via a source reference. Subsequently select the Type in which the Source Reference can be found and in which column / value within this Import Template the data for the Source Reference can be found.
* If data is imported to a Location Reference, select the Type and Sub-Object to be used for the Location Reference.
* If data is imported to Object Sources, select the Type in which the Source Reference can be found and in which column / value within this Import Template the data for the Source Reference can be found.

Click the grey 'run import template' button to run the Import Template. Select a source file to use and the row to start. Click Run to start the import process. By default, the import process will stop at every row and display the values assigned to your Data Model. You can then either add the new Object, or discard the new Object and proceed to the next row.

Use the option following options to change the behaviour of the import process:

* Select '**Disallow Object Creation**' to prevent the import process from creating new Objects in this Type. Existing Objects in this Type may be enriched with new Object Descriptions and/or new Sub-Objects. Example: new participants (Sub-Objects) may be added to an event (Object). But new events (Objects) may not be generated.
* Select '**Instantly Create new Objects**' to instantly create a new Object if no similar Objects were found within this Type.
* Select '**Instantly Append new Sub-Objects**' to instantly append new Sub-Objects to a pre-existing Object. This action will be performed only if one similar Object was found. Example: Participants (Subobjects) may be appended to a pre-existing event (Object).
* Select '**Instantly Append new Object Descriptions**' to instantly append new Object Descriptions to a pre-existing Object. This action will be performed only if one similar Object was found. Example: a honorary title (Object Description) may be appended to a pre-existing person (Object).
* Select '**Instantly Append new Sources**' to instantly append new Sources.
* Select '**Instantly Discard Identical**' to instantly discard new Objects identical to a pre-existing Object.
* Select '**Instantly Discard Empty**' to instantly discard empty Objects.

While you are instantly creating new Objects, the template halts if it finds any ambiguity. You have the ability to select which of the presented options you want to use. You can save this ‘string to Object pair’ by selecting the checkbox at the end of this line.

Importing relational data can best be achieved by importing data per Type / Classification.