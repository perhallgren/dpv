# DPVCG
Data Privacy Vocabularies and Controls Community Group (DPVCG) repository

[Community Group](https://www.w3.org/community/dpvcg/) | [(W3C) wiki](https://www.w3.org/community/dpvcg/wiki/Main_Page)

The mission of the W3C Data Privacy Vocabularies and Controls CG (DPVCG) is to develop a taxonomy of privacy and data protection related terms, which include in particular terms from the new European General Data Protection Regulation (GDPR), such as a taxonomy of personal data as well as a classification of purposes (i.e., purposes for data collection), and events of disclosures, consent, and processing such personal data.

Outputs:
  * Data Privacy Vocabulary (DPV) - [https://w3.org/ns/dpv](https://w3.org/ns/dpv)
  * GDPR terms for Data Privacy Vocabulary (DPV-GDPR) [https://w3.org/ns/dpv-gdpr](https://w3.org/ns/dpv-gdpr)

Publication: 
 * Pandit H.J. et al. (2019) Creating a Vocabulary for Data Privacy. In:  Panetto H., Debruyne C., Hepp M., Lewis D., Ardagna C., Meersman R.  (eds) On the Move to Meaningful Internet Systems: OTM 2019 Conferences.  OTM 2019. Lecture Notes in Computer Science, vol 11877. Springer, Cham.  https://doi.org/10.1007/978-3-030-33246-4_44

## Data Privacy Vocabulary (DPV)

The Data Privacy Vocabulary provides terms (classes and properties) to annotate and categorize instances of legally compliant personal data handling according to the EU General Data Protection Regulation. This scope could be extended by later versions to other data and privacy protection regulations. 

The vocabulary provides terms to describe:

* purposes of processing
* personal data categories involved
* processing operations
* technical and organisational measures or restrictions applied
* legal basis used to justify processing
* information about legal basis for processing
* rights as applicable
* risks as applicable

The namespace for DPV terms is `http://www.w3.org/ns/dpv#` with suggested prefix `dpv`. The IRI for DPV is currently redirected to serve the files hosted in this repository from GitHub pages i.e. `https://w3c.github.io/dpv/dpv/` (thanks to @bert-github for setting this up). Content-negotiation should therefore be supported for all files/serialisations of the DPV and its modules.

### DPV-GDPR

The [**DPV-GDPR**](https://w3.org/ns/dpv-gdpr) vocabulary expands on the DPV vocabulary to provide the specific legal basis, rights, and concepts defined within GDPR. It expands or specialises the concepts in DPV for use with GDPR.

### DPV-NACE

The [**DPV-NACE**](https://github.com/w3c/dpv/tree/master/dpv-nace) vocabulary provides a RDFS and DPV compatible serialisation of the  [NACE](https://ec.europa.eu/eurostat/ramon/nomenclatures/index.cfm?TargetUrl=LST_NOM_DTL&StrNom=NACE_REV2) industry standard classification system used in the EU.

### DPV and Modules

The term 'DPV' represents the entire vocabulary - with its concepts and terms as defined in the specification. Serialisations for this in `rdf+xml`, `json-ld`, and `turtle` are provided. The 'modules' in DPV are separate files for each of the hierarchies and concept taxonomies - for example 'purposes'. These are defined in the `rdf` folder with serialisations for each module. The `core` or `base` vocabulary or ontology is defined containing the top-level classes and data model (i.e. `PersonalDataHandling`).

## Contribution / Participation

The DPVCG is the primary forum for contributions and participations regarding the DPV. As such, all decisions and resolutions will be conducted through the group's meetings and call. Membership in DPVCG is not necessary to contribute to DPV, but is recommended for participating in the group's decision making process. Contributions and questions can be sent to the group's [public mailing list](https://lists.w3.org/Archives/Public/public-dpvcg/) or expressed as [GitHub issues](https://github.com/dpvcg/dpv/issues). 

## Suggesting new terms

To suggest a new term, we request following information:

* _term_ 
* _description of the term_
* whether it should be a _class_ or _a property_
* relation to existing term(s) in DPV e.g. through sub-classes
* source (where applicable)
* justification or relevance of why this term should be added (where not obvious)

### Raising issues

Before submitting an issue, please see the whether the issue has been addressed on [GitHub](https://github.com/w3c/dpv/issues). If not, please raise the issue via the group's [public mailing list](https://lists.w3.org/Archives/Public/public-dpvcg/) or expressed as [GitHub issues](https://github.com/w3c/dpv/issues). 

Fixes, corrections to the terms are considered as issues and can be submitted similarly. For minor changes, we may prefer to incorporate them directly rather than through pull requests and patches. For larger issues, please check with the group before submitting a pull-request to ensure its appropriate and efficient incorporation.

## Development Guide

> please refrain from making changes by-hand or manually

The development and maintainence of DPV takes place primarily through a shared spreadsheet. The terms and their annotated metadata are declared in the spreadsheet, and used as input to generate the RDF files and HTML documentation through the [documentation-generator](https://github.com/w3c/dpv/tree/master/documentation-generator) tooling. The `documentation` tool is a collection of Python scripts to assist in the automation of downloading the spreadsheet as CSV files, generating RDF files, validating them for correctness, and producing the HTML documentation.

Therefore, whenever adding a new term or changing existing ones, the following steps are recommended to update the DPV vocabulary and documentation:

1. Make changes appropriately in the shared spreadsheet. The links to this are available to the DPVCG members.
2. Use the [documentation-generator](https://github.com/w3c/dpv/tree/master/documentation-generator) tooling to download the spreadsheet, generate RDF, test it, generate HTML output. 
3. Manually inspect whether the changes have been made. Tools, scripts, and software in general can propogate errors silently. 
4. The variables and parameters in  [documentation-generator](https://github.com/w3c/dpv/tree/master/documentation-generator) tooling can be used to define the path where files are exported to can be set to the `dpv` repository to make changes in this directory. For e.g. `EXPORT_DPV_HTML_PATH = ~/code/dpvcg/dpv` will generate the HTML documentation in the `dpv` directory. 
5. Submit a pull-request for merging with the repository.

## Getting help and assistance

If you're unsure about something, or would like clarifications, or suggestions - please drop us a line or open an issue. We would be happy to help.