# Music Encoding Initiative (MEI)
This projects includes some experiments in querying MEI/XML with SPARQL Anything.

This project includes examples using open data from the Tate Gallery collection.

In what follows, `fx` is `java -jar sparql-anything-<version>.jar`.
	
## An MEI XML in Facade-X/RDF
```
fx -q queries/toRDF.sparql -o data/toRDF.ttl -f TTL
```

## File description
```
fx -q queries/file.sparql -o data/cnw0001-file.csv -f CSV
```

## Bibliography
```
fx -q queries/bibl.sparql -o data/cnw0001-bibl.csv -f CSV
```

## Draft ontology
```
fx -q queries/ontology.sparql -o data/ontology.csv -f TTL
```

## Note sequences
```
fx -q queries/notes.sparql -s 0 -v staffNo=1
```
