# Music Encoding Initiative (MEI)
This projects includes some experiments in querying MEI/XML with SPARQL Anything.

The queries reuses MEI files from (The Catalogue of Carl Nielsen's Works](https://music-encoding.org/projects/cnw.html) and from the MEI samples-encoding repository.

This project includes examples using open data from the Tate Gallery collection.

In what follows, `fx` is `java -jar sparql-anything-<version>.jar`.

## An MEI XML in Facade-X/RDF
Transform a complete MEI in RDF:
```
fx -q queries/toRDF.sparql -o data/toRDF.ttl -f TTL
```
And with file `sample-encodings/MEI_4.0/Music/Complete_examples/Parker-Gillespie_ShawNuff.mei`:
```
fx -q queries/toRDF-parker.sparql -o data/Parker-Gillespie_ShawNuff.ttl -f TTL
```

## File description
```
fx -q queries/file.sparql -o data/cnw0001-file.csv -f CSV
```

## Bibliography
List bibliographic statements in `CNW/cnw001.xml`
```
fx -q queries/bibl.sparql -o data/cnw0001-bibl.csv -f CSV
```

## Draft ontology
Query file `CNW/cnw0001.xml` and declare OWL classes, object properties, and datatype properties.

```
fx -q queries/ontology.sparql -o data/ontology.csv -f TTL
```

## Note sequences
This query extract the list of notes from `sample-encodings/MEI_4.0/Music/Complete_examples/Parker-Gillespie_ShawNuff.mei`.

To see the list in the terminal:
```
fx -q queries/notes.sparql
```

`staffNo` is an optional parameter, otherwise both staffs are returned

```
fx -q queries/notes.sparql -v staffNo=1
```
Save as CSV:
```
fx -q queries/notes.sparql -d data/notes.csv -f CSV
```

