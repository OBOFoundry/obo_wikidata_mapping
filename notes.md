Wikidata notes (split out and add link?)
----------------------------------------

### General wikidata learning: 

#### Wikidata entities:

[*Items*](https://www.wikidata.org/wiki/Help:Items)
-   have a [*label*](https://www.wikidata.org/wiki/Help:Label), [*description*](https://www.wikidata.org/wiki/Help:Description), [*alias*](https://www.wikidata.org/wiki/Help:alias) - All have 250 char limit. Description is specifically short text for disambiguation, probably not suitable for OBO ontology definitions. Alias can be used for OBO exact synonym
-   May have arbitrary number of properties

Properties, including:
-   Properties that encode identifiers
-   Properties that have text (string) as a value - have a 400 (UTF-8 unicode) char limit.
-   Properties that relate 2 items. e.g.:
    -   subClass of (could be used for ontology subclassing)
    -   part of
    -   instance of (could be used for ontology links to data)
    -   follows (could potentially be extracted from timing relationships in OWL)

Qualifiers:
-   modify the meaning of the value of a property (?)

### Mapping existing info to wikidata

#### Importing OBO ontologies into wikidata

##### How to grab the latest version of an OBOish OWL ontology?
> Use the generic PURL, e.g, [*http://purl.obolibrary.org/obo/*](http://purl.obolibrary.org/obo/)go.owl
>
> OR query OLS (?)

#### IDs

Generic import should specify how to use [*OBO-foundry PURL IDs*](http://obofoundry.org/id-policy.html). 
PURLS follow a consistent pattern, but the following details vary in each ontology
 *  ID prefix
 *  numeric component
    1.  Fixed length (boolean)
    2.  Length

### Annotation property mapping
1.  Generic import should specify annotation property mappings from the official OBO to OWL specification to wikidata properties/items/built-ins, adding new properties as needed. Main properties to map are:
    1.  On ontology:
        1.  Version IRI
        2.  ...
    2.  On terms
      -   label: [*http://www.w3.org/2000/01/rdf-schema\#label*](http://www.w3.org/2000/01/rdf-schema#label) :
      -   definition: [*http://purl.obolibrary.org/obo/IAO\_0000115*](http://purl.obolibrary.org/obo/IAO_0000115) : TODO propose new property. Will have 400 char limit. Check how many will be truncated as a result. (Or link out to definition elsewhere?)
      -   comment: [*http://www.w3.org/2000/01/rdf-schema\#comment*](http://www.w3.org/2000/01/rdf-schema#comment) - **Don't map**.
      -   synonym (question: do we distinguish synonym types?)
         1.  [*http://www.geneontology.org/formats/oboInOwl\#hasBroadSynonym*](http://www.geneontology.org/formats/oboInOwl#hasBroadSynonym) Request new wikidata property?
         2.  [*http://www.geneontology.org/formats/oboInOwl\#hasExactSynonym*](http://www.geneontology.org/formats/oboInOwl#hasExactSynonym) MAP TO wikidata:alias
         3.  [*http://www.geneontology.org/formats/oboInOwl\#hasNarrowSynonym*](http://www.geneontology.org/formats/oboInOwl#hasNarrowSynonym) Request new wikidata property?
         4.  [*http://www.geneontology.org/formats/oboInOwl\#hasRelatedSynonym*](http://www.geneontology.org/formats/oboInOwl#hasRelatedSynonym) Request new wikidata property?
      - dbxref :[*http://www.geneontology.org/formats/oboInOwl\#hasDbXref*](http://www.geneontology.org/formats/oboInOwl#hasDbXref)
        1.  On definition
        2.  On term - map to wikidata:'see also'

1.  Where database xrefs are used they should follow [*db-xrefs.yaml*](https://github.com/geneontology/go-site/blob/master/metadata/db-xrefs.yaml). This is used by multiple OBO resources.
2.  Consider adding links to wikidata in [*db-xrefs.yaml*](https://github.com/geneontology/go-site/blob/master/metadata/db-xrefs.yaml)

    1.  But be careful re: how to deal with typing and disambiguation: ebola is a rock band as well as a disease. Better to use bipartite specification: type:name

#### Links wiki-(data/pedia) &lt;-&gt; obo ontologies

Generic ontology resources to link to that include all (?) OBO ontologies
-   ontology lookup service
-   NB: [*https://www.wikidata.org/wiki/Q4117183*](https://www.wikidata.org/wiki/Q4117183) exists
Ontology specific:
  - GO specific:
    - QuickGO
    - AmiGO
  -  Drosophila anatomy
    - VirtualFlyBrain

#### Implementation 

Q. Which OBO abstractions should live in wikidata vs in specification mapping specification for import bots.
A. Abstraction should live in mapping documents.  Mapping documents should be on wikidata (where?)

