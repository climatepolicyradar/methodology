# Corporate Disclosures Pilot Project Methodology

## Summary

This pilot project established an open, structured and searchable database of corporate climate disclosures to test the value of this to actors who use them – particularly those who regularly gather disclosures at scale. It compiled over 900 documents published by more than 450 companies worldwide, including regulatory filings, climate plans, and integrated reports.

This pilot dataset provides a snapshot of publicly available information accessible between 6 February and 28 May 2025\. It is not a continuously updated resource. Subject to available resources and evolving research priorities this provides a foundation for potential future iterations, which may include more companies or document types.

We welcome [feedback on this pilot](https://form.jotform.com/251592717521357) as we decide if this work is continued.

## Project scope and definitions used for data collection

The pilot focused on 463 publicly-listed companies, derived from a seed list of 467 companies extracted from [TransitionArc](https://transitionarc.climatearc.org/faqs/) and 10 companies proposed by the [United Nations Environment Programme Finance Initiative](https://www.unepfi.org/).

The primary focus and scope of the pilot was on parent company disclosures, so the seed list was transposed to contain as many parent companies as possible. If the parent entity did not appear to publish relevant documents, disclosures from relevant subsidiaries were included and attributed to the subsidiary.

The scope of data collection was limited to the most recent, publicly-available corporate disclosures at the time of research. The research process was intentionally flexible, allowing identification of a broad range of document types relevant to climate-related governance. The following document categories were used to classify and organise corporate disclosures:

* **Annual Mandatory Filing**: Documents submitted to national regulatory authorities containing core financial and operational disclosures. These are typically required by law and provide a standardised baseline of information.  
* **Financial Year Report**: Alternative or supplementary annual reports that detail a company’s commercial activity, results, and sometimes projections of financial assets. These may present information in formats different from those required by regulators and/or may contain additional or more granular data.  
* **Integrated Annual Report**: Type of report that aligns business strategy and financial results with environmental performance, and social strategies, offering a holistic account of a company’s economic and sustainability performance over the financial year.  
* **Corporate Transition Plan**: Broadly defined here as reports disclosing a company’s strategy and actions to reduce greenhouse gas (GHG) emissions. These may include sector-specific pathways, targets, and implementation mechanisms for achieving decarbonisation.  
* **Carbon Disclosure Project (CDP) Report**: Structured responses to CDP’s standardised questionnaire.  
* **Global Reporting Initiative (GRI) Report**: Sustainability reports prepared according to the GRI Standards.  
* **Task Force on Climate-related Financial Disclosures (TCFD) Reports**: Disclosures structured around the TCFD’s four pillars: governance, strategy, risk management, and metrics and targets.  
* **CO₂ Emissions Report**: Standalone reports disclosing company-level CO₂ emissions. These typically include Scope 1 (direct emissions), and where available, Scope 2 (indirect emissions from energy use) and Scope 3 (value chain emissions). Such reports were included when more comprehensive disclosures were not available or were used as supplementary materials.  
* **Climate Adaptation and Risk Report**: Specialised report focused on a company’s strategies and actions related to climate adaptation and risk management. These were included when companies chose to report such information separately or as an alternative to other disclosures.  
* **Sustainability or ESG Reports**: Generic reports that typically provide the most direct articulation of a company’s sustainability strategy.  
* **Environmental Reports**: Standalone documents outlining a company’s environmental performance, policies, and impacts.

## Methods: process of data collection and organisation

Data collection was conducted between 6 February and 28 May 2025\. It followed a structured desktop research protocol to guide the search, selection, and metadata entry processes for each company included in the pilot.

### Search protocol

Determining whether an entity was a parent company or a subsidiary was based on declarations made by companies in their own reports, corporate websites, and other publicly available sources. Searches for relevant reports were conducted via the websites of company and national financial regulators. The project focused exclusively on publicly accessible documents. At least one document was collected per company.

### Country classification criteria

Each report was associated with the company that published it, and each company was linked to the country in which it declared its legal constitution and headquarters. The CPR platform uses ISO3 Alpha-2 & Alpha-3 country codes for standardised classification. However, three jurisdictions (Bermuda, the Cayman Islands, and Jersey) are not recognised as countries within the ISO3 list. In these cases, companies registered in those jurisdictions were assigned to the United Kingdom, reflecting their legal or constitutional ties to the UK or the British Crown.

### Metadata documentation: dates, names, and PermID information

Relevant documents were processed and recorded in a centralised Google spreadsheet with the following metadata fields included:

* Document title  
* Document type  
* Year of publication  
* Source URL  
* Document language  
* Company name  
* Country of company headquarters  
* [PermID](https://permid.org/) Uniform Resource Identifier (URI) of company

On date conventions, CPR’s interface uses the full date (day–month–year) of publication. When this was available, it was recorded. If only the month and year were specified, the first day of the month was used (e.g. 01/07/2022). If only the year was available, the default date assigned was 31 December of that year (e.g. 31/12/2021). There may be discrepancies between the year of publication recorded in this way and dates visible in the titles of documents which often refer to reporting periods that are the focus of documents, especially if there’s a substantial lag between the reporting period and publication.

A consistent naming convention distinguishes between two levels of labelling. The first level is the entry name, referred to as a “family” in the CPR interface. This is the standardised title shown in the main database view. It follows this structure:

**\[Company name\] \+ \[Type of report according to classification above\] \+ \[year\]**

**Example**: Latam Airlines Group S.A. Annual Mandatory Report 2024

The second level **(ii)** is the actual report name. This is the original title of the report, as published by the company. It preserves the specific naming chosen by the company:

**\[Title of the document as given by the company\]**

**Example** (from the 2023 Corporate Transition Plan of Lendlease Corporation Ltd.):  
Mission Zero Roadmap: 2023 Progress Report

If the document was published in a language other than English, we provide a bilingual label that includes both an English translation and the original title, to support accessibility across languages:

**\[Translated English title\] \+ (Original title in native language)**

**Example** (from Redes Energéticas Nacionais, SGPS, S.A).: Integrated Report 2023 (Relatório Integrado 2023\)

Each family entry included the company’s PermID URI, with one exception where this was not locatable (CLP group). All documents gathered were uploaded to the CPR database along with a subset of the metadata collected.

## Limitations

Certain limitations are inherent to the project’s design – the unstructured nature of corporate climate data, and practical constraints of time and resources. This section outlines key limitations and the strategies adopted to mitigate their effects: 

### Public-sector companies

Public-sector entities that operate in the market often adopt hybrid forms shaped by national regulatory, economic, and legal cultures. For the purposes of this project, such entities were treated as companies if they engaged in market-based activities and disclosed climate-related information in ways comparable to private-sector firms. Where applicable, further detail on the public–private nature of each entity is available in its associated metadata, including reports and PermID information.

### Search environment and language bias

The vast majority of searches were conducted in English and performed using UK-based computers and internet protocols. Consequently, documents hosted in non-English formats or on regionally optimised platforms may have been underrepresented in search results.

To mitigate this, researchers conducted structured navigations of official company websites and employed standardised search terms. Nevertheless, future iterations may benefit from multilingual search capabilities and geolocated browsing environments to broaden access to regionally hosted or non-English disclosures.

### Human error

Some documents may have been missed or misclassified. In some cases, classification required interpretative judgment—for example, determining whether a hybrid document should be categorised as “annual”, “integrated”, or “voluntary”.

### Reliance on publicly available data

The pilot used only publicly available documents and excluded reports not published online, reports hosted on paywalled platforms, and disclosures made to regulatory authorities without public dissemination. 

### Evolving reporting landscape

Corporate climate reporting practices are dynamic, so documents included in this pilot may have been superseded shortly after collection or reflect transitional practices between regulatory regimes. Users are encouraged to consult original sources for the most current and authoritative information.

### Categorisation of reports as mandatory and voluntary

Few companies explicitly declare whether a given report is mandatory (i.e. required to be filed with regulatory authorities or made publicly accessible by law) or voluntary (i.e. disclosed at the discretion of the company). Many jurisdictions do not require public access to mandatory filings, or restrict access through fee-based system. And regulatory standards vary widely across countries, and sometimes within them.

If the mandatory nature of a document could not be established, the report was recorded as voluntary to avoid overrepresenting regulatory compliance. Users requiring a precise classification should consult jurisdiction-specific rules applying to the specific entity and the company’s official statements to determine the legal status of a report.

## How users can contribute or flag errors

We welcome [feedback on this pilot](https://form.jotform.com/251592717521357) to help understand if it’s useful and how it could be improved. If you’d like to report issues or have additional suggestions, please get in touch via [support@climatepolicyradar.org](mailto:support@climatepolicyradar.org). Your contributions help us to sustain this open data initiative.
