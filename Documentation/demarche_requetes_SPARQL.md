PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/> 
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?person ?label
WHERE {
SERVICE <https://dbpedia.org/sparql> {
    dbr:17th-century_Italian_painters ?p ?person.
    ?person a dbo:Person;
        FILTER (LANG(?label) = 'en')
    }
}


Donc d'abord on fait le truc ci-dessus.

Ensuite un construct:
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/> 
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>


CONSTRUCT {?person rdfs:label ?label;
                    a dbo:Person;
                    dbo:birthYear ?bYI.
           }
WHERE {
SERVICE <https://dbpedia.org/sparql> {
    dbr:peintres_17e ?p ?person.
    ?person a dbo:Person;
            dbo:birthDate ?birthDate ;
        rdfs:label ?label.
        BIND(xsd:integer(SUBSTR(STR(?birthDate), 1, 4)) AS ?birthYear)
        FILTER ( ?birthYear > 1770  && LANG(?label) = 'en')
    }
  
}

Ensuite on fait un insert:
PREFIX dc:  <http://purl.org/dc/elements/1.1/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

INSERT 
  { GRAPH <http://example/bookStore2> { ?book ?p ?v } }
WHERE
  { GRAPH  <http://example/bookStore>
       { ?book dc:date ?date .
         FILTER ( ?date > "1970-01-01T00:00:00-02:00"^^xsd:dateTime )
         ?book ?p ?v
  } }	





Dans le langage SPARQL c'est dans WHERE qu'on voit la structure. 