# obo\_wikidata\_mapping

STATUS: ROUGH DRAFT

A repo discussion and specification of mappings to wikidata from ontologies in OWL that follow the OBO 1.4 standard for annotation properties and the OBO Foundry standard ID specification.

notes.md contains some general notes on mapping written during SWAT4LS2015 hackathon.

There are at least a couple of options for starting points for mapping:

1. Direct parsing of OWL files.  Draft mapping in yaml in obo\_wikidata\_mapping.yml
2. From [OLS API](http://www.ebi.ac.uk/ols/beta/docs/api) - draft mapping table: OLS\_mapping.tsv. Table based on ['retrieve a term' query](http://www.ebi.ac.uk/ols/beta/docs/api#_retrieve_an_term). 

The OLS API is appealing for a number of reasons:
 - One central location for all the latest versions of OBO ontologies
 - It is much easier to query and to work with results than tools working directly with rdf or owl.
 - It hides some complexity:
    - provides a graphy representation for both classification and key relation types (part\_of, develops\_from)
    - xref on term (provisional mapping WD:'see also') vs xref on definition (new wikidata property) - (pending addition to https://github.com/EBISPOT/OLS/issues/2)


 
