# obo\_wikidata\_mapping

STATUS: ROUGH DRAFT

A repo discussion and specification of mappings to wikidata from ontologies in OWL that follow the OBO 1.4 standard for annotation properties and the OBO Foundry standard ID specification.

### Motiviations: 

1. Linkouts from wikipedia to resources displaying annotations to ontology terms.
 * **Why?** Added value for WP: Provides links from, for example, biological processes on WP to lists of genes involved. Added value for ontology resources: Traffic.
 * **How?** Wikidata is used to populate info boxes on Wikipedia. Loading ontologies into Wikidata - with mapping of terms to Wikidata entries corresponding to Wikipedia pages, provides a potential route for linkouts from Wikipedia info boxes.
2. Wikidata has broader ambitions as a curated respository of linked-data. It is in the interests of those developing ontologies to be part of this, especially if the work required is minimal.

### Mapping issues:

1. How to map from wiki-(data/pedia) items to onotology terms:
 * Likely solution: A mix of harvesting curated mappings from xrefs and lexical mapping.
1. ID mapping from the OBO Foundry URI standard.
1. Mapping annotation properties to wikidata properties/built-ins
 * Note that there are character limits on the wd side.
1. What resources should be linked out to?  
 * There are limits on this set by WD, and any linkouts would need community approval.

Please see notes.md for general notes on mapping written during SWAT4LS2015 hackathon.

### Some starting points for mapping:

1. Direct parsing of OWL files.  Draft mapping in yaml in obo\_wikidata\_mapping.yml
2. From [OLS API](http://www.ebi.ac.uk/ols/beta/docs/api) - draft mapping table: OLS\_mapping.tsv. Table based on ['retrieve a term' query](http://www.ebi.ac.uk/ols/beta/docs/api#_retrieve_an_term). 

The OLS API is appealing for a number of reasons:
 - One central location for all the latest versions of OBO ontologies
 - It is much easier to query and to work with results than tools working directly with rdf or owl.
 - It hides some complexity:
    - provides a graphy representation for both classification and key relation types (part\_of, develops\_from)
    - xref on term (provisional mapping WD:'see also') vs xref on definition (new wikidata property) - (pending addition to https://github.com/EBISPOT/OLS/issues/2)


 
