## Example of SPARQL query
tested on a local instatiation of GraphDB by Ontotext (with reasoning set to OWL2 QL)

```sparql
PREFIX : <http://www.textualpatterns.org#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
SELECT ?poem ?variant ?titleCollection ?publisherName ?pubYear WHERE { 
    ?poem a :Text;
          :hasVariantType ?variant;
       :hasTitle "Al di là della speranza";
       :includedIn ?collection.
    ?collection a :Text;
        :hasTitle ?titleCollection;
        :hasSituation ?s.
    ?s a :PublicationSituation;
       :hasPublisher/rdfs:label ?publisherName;
        :hasPublicationYear ?pubYear} 
```
Result of query:
![Local Image](text-query-result.png)

