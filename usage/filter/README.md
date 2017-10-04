## Filter
Click the funnel icon at the top of the overview of Objects, Categories, or Reversed Classifications to open the Filter functionality. The Filter functionality reflects the Data Model. Everything that has been configured in the Data Model can be queried via the Filter functionality.

Click the blue 'save' button to save the currently active filter configuration. The tab 'Advanced' shows a JSON representation of the current filter configuration that can be used when using the API to query nodegoat.

Click the green 'open' button to open a previously saved filter configuration. The tab 'Advanced' can be used to paste a JSON representation of a nodegoat Filter configuration.

### Addition Filter / Reduction Filter
To perfom multiple queries at once (i.e. `AND`/`OR`-queries), click the green 'open' button and select an empty (new) or a previously saved filter. An additional tab will appear. To specify how multiple tabs relate to each other, you configure each tab to be an 'Addition Filter' (`OR`) or a Reduction Filter (`AND`). For the Reduction Filter, you can specify the number of previous filters it should affect (n = x).

### Exclude
By default the Filter is configured to include the elements that return true on the active filter configuration. To reverse this behaviour, check 'Soft Exclude' or 'Hard Exclude'. The distinction between 'Soft Exclude' and 'Hard Exclude' only applies when filtering multi-value references and non-unique Sub-Objects. A 'Soft Exclude' filter will only exclude their values on matched filtering, while a 'Hard Exclude' filter excludes the whole Object on matched filtering.

### Objects
Use the 'Objects' search bar to include one or more Objects, Categories, or Reversersed Classifications in the filter results. This input field functions as the [quicksearch bar](/usage/data_view/README.md#quicksearch). Click the green 'add' button to add additional input fields. Click the red 'del' button to remove empty input fields.

### Descriptions
The Descriptions that have been defined in the Data Model are listed, with a '+' button trailing the name of the Description. Click on the '+' button to open the Description as an input field. Click the green 'add' button to add additional input fields. Click the red 'del' button to remove empty input fields.

Click the grey 'more' button to specify whether this Description should contain any values or not.

* Any (default), the Description may be empty or not empty.
* Not Empty, the Description should contain a value.
* Empty, the Description should not contain a value.

Use the following operators to specify the behaviour of the filter while filtering numerals, dates or the number of returned valid responses:

* = (default), exact match.
* &lt;, less than the entered value.
* &gt;, greater than the entered value.
* ≤, equal or less than the entered value.
* ≥, greater or less than the entered value.
* &gt; a &lt; b, in between the entered value.
* ≥ a ≤ b, equal or in between the entered value.

All Descriptions containing strings can be queried using the following equality operators:

* \* (default), the Description should contain an occurance of the entered string.
* a\*, the Description should start with the entered string.
* \*a, the Description should end with the entered string.
* =, the Description should be an exact match of the entered string.

#### Type, Classification, Reversed Classification, Location Reference, Sub-Object Descriptions
Relational Descriptions allow you to create filters based on relationships. Find the desired target by performing a [quicksearch](/usage/data_view/README.md#quicksearch) using the input field or click the grey 'filter' button to find the target using the Filter functionality.

Next to the red 'del' button and the green 'add' button, a green 'filter' button allows you to filter the referenced elements. Click the green 'filter' button to open an existing filter or a new (empty) filter. At the top of the Filter popup, the tab from which this new filter was added is supplemented with a new tab that contains information about the referencing Description and the target Type, Classification or Reversed Classification.

#### True/False
Select a value to filter on.

### Sub-Objects
The Sub-Objects that have been defined in the Data Model are listed, with a '+' button trailing the name of the Sub-Object. Click on the '+' button to open the Sub-Object as a filter form. Using the 'Sub-Objects: Any' filter form you can create a filter that performs a filter on all available Sub-Objects.

#### Amount
Specify the amount of Sub-Objects

#### Date
Select a date range or a date point during which Sub-Objects should exist.

##### Date From / Date To
Specify a range.

##### Date Start / Date End
Specify a point.

#### Location
Select Reference to filter on Location References, select Point to filter on a latitude and longitude values, select Area to filter on a polygon. Click the grey 'more' button to show an input field to specify a radius to filter on.

##### Location Reference
Specify the Type to be used for the Location Reference and select the Sub-Object of this Type used for the filtering.

##### Point
Fill in latitude and longitude values, or use the green 'map' button to select a location on the map.

##### Area
TBA

### Cross-Referenced
Filter on incomining references by selecting the kind of incoming reference: 'Any', 'Object Descriptions', 'Sub-Object Descriptions', or 'Sub-Object Locations' and specify the amount of incoming references by clicking on the grey 'more' button.

Incoming references are lister per Type and/or Classification in a seperate tab. Each incoming reference of another Type/Classification can be filtered on seperately or together by using the Cross-Referencing option. Click the green 'filter' button to open an existing filter or a new (empty) filter to filter on the referenced Type/Classification.

### Version and Users
Filter on versioning by selecting one or more versions. You can filter on actions taken on an Object, Categorie or Reversed Classification by specifying whether it has been audited or not. Specify a Date Start and Date End to filter on when an Object, Categorie or Reversed Classification was changed. You can filter to include or exclude Objects, Categories or Reversed Classifications handled by yourself or other users.