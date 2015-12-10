# obo_wikidata_mapping

STATUS: ROUGH DRAFT

A repo for files specifying mapping between OBO-ish owl ontologies and wikidata.  There are at least a couple of possible routes for this:

1. Direct parsing of OWL files
2. From OLS API

OLS API is appealing for a number of reasons:
 - It is much easier to work with
 - It provides a graphy representation for both classification and key relation types (part\_of, develops\_from)
