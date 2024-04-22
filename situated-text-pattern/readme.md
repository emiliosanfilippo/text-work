## Example of SPARQL query
tested on a local instatiation of GraphDB by Ontotext (with reasoning set to OWL2 QL)

```sparql
PREFIX : <http://www.textualpatterns.org#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?poem ?variantType?collectionTitle ?publisherName ?pbYear WHERE {
    ?poem a :SituatedText; 
          :hasTitle "Al di là della speranza";
          :hasVariantType ?variantType;
          :includedIn ?collection.
    ?collection a :SituatedText;
                :hasTitle ?collectionTitle;
                :hasPublisher/rdfs:label ?publisherName;
                :hasPublicationYear  ?pbYear}
```
Result of query:

![Local Image](situated-text-query-result.png)

Example of RDF graph (it shows two texts, one for the full-variant, one for the shortened-variant)

![Local Image](situated-text-graph-example.png)
