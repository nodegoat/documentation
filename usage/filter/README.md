## Filter
Click the funnel icon at the top of the overview of Objects, Categories, or Reversed Classifications to open the Filter functionality. The Filter functionality reflects the Data Design. Everything that has been configured in the Data Design can be queried via the Filter functionality.

Click the blue 'save' button to save the currently active filter configuration. The tab 'Advanced' shows a JSON representation of the current filter configuration that can be used when using the API to query nodegoat.

Click the green 'open' button to open a previously saved filter configuration. The tab 'Advanced' can be used to paste a JSON representation of a nodegoat Filter configuration.

### Addition Filter / Reduction Filter
To perfom multiple queries at once (i.e. `AND`/`OR`-queries), click the green 'open' button and select an empty (new) filter. An additional tab will appear. To specify how multiple tabs relate to each other, you configure each tab to be an 'Addition Filter' (`OR`) or a Reduction Filter (`AND`). For the Reduction Filter, you can specify the number of previous filters it should affect (n = x).

### Exclude
By default the Filter is configured to include the elements that return true on the active filter configuration. To reverse this behaviour, check 'Soft Exclude' or 'Hard Exclude'. The distinction between 'Soft Exclude' and 'Hard Exclude' only applies when filtering multi-value references and non-unique Sub-Objects. A 'Soft Exclude' filter will only exclude their values on matched filtering, while a 'Hard Exclude' filter excludes the whole Object on matched filtering.

### Objects
Use the 'Objects' search bar to include one or more Objects, Categories, or Reversersed Classifications in the filter results. This input field functions as the [Quicksearch bar](../data_view/README.md#quicksearch). Click the green 'add' button to add additional input fields. Click the red 'del' button to remove empty input fields.

### Descriptions
The Descriptions that have been defined in the Data Design are listed, with a '+' button trailing the name of the Description. Click on the '+' button to open the Description as an input field. Click the green 'add' button to add additional input fields. Click the red 'del' button to remove empty input fields.

Click the grey 'more' button to specify whether this Description should contain any values or not.
* Any (default), the Description may be empty or not empty.
* Not Empty, the Description should contain a value.
* Empty, the Description should not contain a value.

#### String, Text, Text (layout), Text (tags & layout)
All Descriptions containing strings can be queried using the following equality operators:
* \* (default), the Description should contain an occurance of the entered string.
* a\*, the Description should start with the entered string.
* \*a, the Description should end with the entered string.
* =, the Description should be an exact match of the entered string.

#### Type, Classification, Reversed Classification
Relational Descriptions allow you to create filters based on relationships. Find the desired target by performing a [Quicksearch](../data_view/README.md#quicksearch) using the input field or click the grey 'filter' button to find the target using the Filter functionality.

Next to the red 'del' button and the green 'add' button, a green 'filter' button allows you to filter the referenced elements. Click the green 'filter' button to open an existing filter or a new (empty) filter. At the top of the Filter popup, the tab from which this new filter was added is supplemented with a new tab that contains information about the referencing Description and the target Type, Classification or Reversed Classification.

Relational Descriptions that can contain multiple values, can be queried on the amount of references they contain. Click the grey 'more' button to show the Empty/Not Empty filter plus the following operators to specify the amount of references:

* = (default), exact amount of references.
* &lt;, less than the entered amount of references.
* &gt;, greater than the entered amount of references.
* ≤, equal or less than the entered amount of references.
* ≥, greater or less than the entered amount of references
* &gt; a &lt; b, in between the entered amounts of references.
* ≥ a ≤ b, equal or in between the enetered amounts of references.


#### Integer

#### Text (tags & layout)

#### True/False

#### Date

#### Media

#### Media (External)

#### External

### Sub-Objects


### Cross-Referenced


### Version


### Users
