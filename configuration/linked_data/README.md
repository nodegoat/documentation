## Linked Data

Linked Data Resources allow you to query API services or SPARQL endpoints by using an External Description. Once you have created one or more Linked Data Resources you can assing a Linked Data Resource to a Description that has been set as 'External' in your [Data Model](/configuration/data_model/type.md#object-descriptions). You can find more information about this functionality in the nodegoat blog post [Linked Data vs Curation Island](https://nodegoat.net/blog.p/82.m/12/linked-data-vs-curation-island).

To add a Linked Data Resource, click 'Add Linked Data Resource'.

To edit an existing Linked Data Resource, click the blue 'edit' button at the relevant Linked Data Resource.

To delete an existing Linked Data Resource, click the red 'del' button at the relevant Linked Data Resource.

Enter a Name for the Linked Data Resource.

Enter a Description for the Linked Data Resource.

Specify whether the Linked Data Resource will be using API requests, SPARQL queries, or if it is a static link.

Enter a URL for the Linked Data Resource (e.g. '_https://query.wikidata.org/bigdata/namespace/wdq/sparql?query=_').

Enter URL Options for the specified URL (e.g. '_&format=json_').

Enter a Query. Use a query you have tested with the API service or SPARQL endpoint. This query should return the identifiers and labels of the data you are interested in. To use this query in as a Linked Data Resource, you can use tags to specify which parts of the query will be changed by the input of the user who uses this Linked Data Resource. A simple SPARQL query like this example: `SELECT ?subject ?label WHERE { ?subject rdfs:label ?label . FILTER (CONTAINS(?label, 'x')) . }` will have to be changed into `SELECT ?subject ?label WHERE { ?subject rdfs:label ?label . [query=name] FILTER (CONTAINS(?label,'[variable]x[/variable]')) . [/query] }` in order for the Linked Data Resource to know that the value of the `?label` can be set by the user.

Using the `[query=name]` tag with at least one `[variable]` is mandatory and is used for initial/quick searches. Additional `[query=x]` tags can be used to perform advanced filtering, everything in between is removed when not filtered on. Multiple `[query=x]` tags can exist that share the same x. `[variable=y]` can be used to label variables (shown in advanced filtering). Multiple `[variable]` or `[variable=y]` tags can exist in a single `[query]` that optionally share the same y. For the API protocol, the inclusion of `[offset]` and `[limit]` tags is mandatory.

Click the green 'test' button to test the Query and to generate a response.

If the query was successful, the query Response field wull be populated with the response of the query.

Click the green 'use' button to use the response to specify the URI, Label, and Values.

Enter a URI Prefix to be used to construct the URI in case the URI only returns an identifier.

Select the field in the response that contains the URI.

Select the field in the response that contains the Label.

Select additional fields in the response that will be shown as Values in the overview of returned objects. Click the green 'add' button to add additional drop-down menus. Click the red 'del' button to remove empty drop-down menus.