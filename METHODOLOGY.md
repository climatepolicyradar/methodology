# Climate Policy Radar Methodology

## Contents

- [Climate Policy Radar Methodology](#climate-policy-radar-methodology)
  - [Contents](#contents)
  - [About this page](#about-this-page)
  - [Documents and sources](#documents-and-sources)
  - [Language](#language)
  - [Updates to the database](#updates-to-the-database)
  - [Data structure](#data-structure)
  - [Document metadata](#document-metadata)
  - [Topics](#topics)
  - [Data limitations](#data-limitations)
  - [Data collection methods](#data-collection-methods)
  - [Natural language search](#natural-language-search)
    - [Biases and limitations](#biases-and-limitations)
  - [Additions and contributions](#additions-and-contributions)
  - [Map projection](#map-projection)
  - [Climate Change Laws of the World](#climate-change-laws-of-the-world)
  - [Multilateral Climate Funds Projects](#multilateral-climate-funds-projects)
  - [Corporate disclosures](#corporate-disclosures)
  - [UNFCCC submissions](#unfccc-submissions)
  - [CBD submissions](#cbd-submissions)
  - [UNCCD submissions](#unccd-submissions)
  - [Offshore Wind Reports](#offshore-wind-reports)

## About this page

The Climate Policy Radar app is the world’s largest open knowledge-base for climate law and policy. Our app allows you to search and explore the full text of 12,000+ climate laws and policies, Nationally Determined Contributions (NDCs), Biennial Transparency Reports (BTRs), corporate climate disclosures and more.

This page provides information about the scope and structure of our database, our data collection methods and terminology, updates to the database and planned future developments.

As we expand and evolve, this methodology document will evolve to reflect developments. 

## Documents and sources

See the [list of data sources](https://app.climatepolicyradar.org/terms-of-use) in our terms & conditions page

## Language

Our dataset contains documents published in many different languages. English-language searches will return auto-translated results from documents in all languages, helping bridge critical information gaps and blindspots. In the future, our user interface will be available in French, Portuguese & all other UN languages.

## Updates to the database

The database is continually monitored and updated by teams of experts at the LSE Grantham Research Institute and Climate Policy Radar, in order to ensure accuracy and to reflect the latest developments in climate law and policy. These updates are drawn from official sources such as government websites and parliamentary records, as well as UNFCCC and related websites, where applicable.

## Data structure

In the Climate Policy Radar database, documents are grouped together with supplementary documents that provide additional information, such as annexes, amendments and press releases, as well as any translations or versions of the document published in other languages.

We also indicate wider relationships between documents. For example, we indicate where documents belong to an overarching policy programme (such as the European Union’s Common Agricultural Policy) or publication cycle (such as Nationally Determined Contributions).

## Document metadata

Documents in the database are assigned attributes (also called metadata) in order to provide information about the contents of documents and to support searchability.

Document metadata applies to entire documents and is manually assigned. Most document metadata and definitions used were developed by the LSE Grantham Institute. For the full list of attributes see our [data dictionary](https://www.notion.so/climatepolicyradar/Readme-for-document-data-download-f2d55b7e238941b59559b9b1c4cc52c5?source=copy_link#b88e072257a24c47b52b4ead774aa30f). The table below provides some example metadata used in the Climate Policy Radar database and app.

| **Attribute**     | **Definition**                                                                                                                                                                                                                                                                                                             |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Jurisdiction | A document’s jurisdiction indicates where it was published. Jurisdictions include all parties to the UN Framework Convention on Climate Change (UNFCCC) — 196 countries plus the European Union — as well as a number of territories which are not party to the UN or UNFCCC, namely Taiwan, Palestine and Western Sahara. |
| Region       | Jurisdictions are grouped into regions of the world, as defined by the [World Bank](https://datahelpdesk.worldbank.org/knowledgebase/articles/906519).                                                                                                                                                                                                                                        |
| Year         | Refers to the year in which a document was first published. Note - this may not be year of the most recent update or amendment to a document.                                                                                                                                                                                                        |


## Topics

Our topics feature automatically identifies mentions of key climate, nature and development concepts in policy and other related documents, connected through our knowledge graph. Topics are developed by domain experts and powered by keyword and AI-based classifiers which are evaluated against human expert-labelled data. This enables users to discover important topics and unlock faster, deeper analysis of documents. In the future, this will be used to improve our other applications like search and generative AI tools. Read the [knowledge graph methodology](https://github.com/climatepolicyradar/methodology/blob/main/knowledge-graph-methodology.md) for more information.

## Data limitations

The principal limitations to our dataset follow from those of our [third-party data providers](https://github.com/climatepolicyradar/methodology/blob/main/METHODOLOGY.md#documents-and-sources).

## Data collection methods

We currently update our database manually, based on monitoring of developments in climate law and policy internationally. We are developing the capacity to more efficiently capture data from additional sources, including via scraping, in order to increase the pace and scope of the expansion of our dataset.

We also currently rely on data labelled manually by domain experts; this limits the pace at which it is possible for new data to be incorporated into our dataset. 

## Natural language search

When you enter a search term and enable 'related phrases' search, the Climate Policy Radar app uses natural language processing (NLP) to help you find relevant content without needing to use exact keywords. This is useful because many concepts can be described in different ways. For example, 'internal combustion engine', 'internal combustion engine vehicle', 'ICEV', 'fossil fuel car', and 'gasoline car' all refer to vehicles commonly found on today’s roads. With natural language search, you can use everyday language, and the tool will recognise related terms, delivering more comprehensive and relevant search results.

We use a machine learning method called dense retrieval alongside a fuzzy string search to perform natural language search. You can find more details [in our blog post](https://climatepolicyradar.org/latest/building-natural-language-search-for-climate-change-laws-and-policies).

### Biases and limitations

The [model](https://huggingface.co/sentence-transformers/msmarco-distilbert-dot-v5) we use for dense retrieval inherits biases from both its base model, [DistilBERT](https://huggingface.co/distilbert-base-uncased#limitations-and-bias), and the search query dataset it was trained on, [MSMARCO](https://github.com/microsoft/MSMARCO-Passage-Ranking/). It’s trained on relatively short passages of text (average 60 words in length), so may struggle with queries longer than this.

At the moment we use a general purpose model that has been trained on English Wikipedia and [BookCorpus](https://arxiv.org/abs/1506.06724v1). This means it may misinterpret some climate- or policy-specific concepts, and is something that we look to improve in future.

For queries we’ve identified that could uncover harmful [biases](https://huggingface.co/distilbert-base-uncased#limitations-and-bias) in the underlying semantic search model, semantic search falls back to using fuzzy string search only,which relies on matching words rather than returning related terms.

## Additions and contributions

We work collaboratively with our expert network of partners and users to ensure our app is accurate and up to date. Should you encounter any errors in the data, we encourage you to get in touch with us at [support@climatepolicyradar.org](mailto:support@climatepolicyradar.org).

## Map projection

This map was made with the [Admin o - Countries](https://www.naturalearthdata.com/downloads/50m-cultural-vectors/50m-admin-0-countries-2/) map package by [Natural Earth](https://www.naturalearthdata.com/). Climate Policy Radar's usage of this World map does not represent an opinion on any disputed boundaries.

## Climate Change Laws of the World

Climate Policy Radar contains laws and policies from the [Climate Change Laws of the World](https://climate-laws.org/) dataset. Please refer to the Climate Change Laws of the World [methodology](https://climate-laws.org/methodology) to read more about this dataset.

## Multilateral Climate Funds Projects

Climate Policy Radar contains publicly available guidance documents and project documentation (such as concept notes, full proposals, implementation reports) from these Multilateral Climate Funds: GCF, GEF, CIF and AF. Please refer to the Climate Project Explorer [methodology](https://climateprojectexplorer.org/methodology) to read more about this dataset.

## Corporate disclosures

Climate Policy Radar now includes 900 regulatory filings, climate plans, and integrated reports published by more than 450 companies worldwide. Please refer to the [Corporate Disclosures Pilot Methodology](https://github.com/climatepolicyradar/methodology/blob/main/corporate-disclosures.pilot-methodology.md) to read more about this dataset.

## UNFCCC submissions

Our database includes country submissions to the UNFCCC including Nationally Determined Contributions (NDCs),  National Adaptation Plans (NAPs), Biennial Transparency Reports (BTRs), Long-Term Low-Emissions Development Strategies (LT-LEDs), National Inventory Reports and National Communications.  These submissions are updated regularly from the UNFCCC's website. 

The database also includes all party and non-party submissions to the first global stocktake.  These documents were last downloaded from the UNFCCC portals on the 24th of May 2023, after the March 2023 cut-off date for inputs to the Global Stocktake.

## CBD submissions

Our database includes a collection of country submissions to the UN Convention on Biological Diversity (CBD) including Nationally Determined Biodiversity Strategies and Action Plans (NBSAPs), National Targets and National Reports. These will be continually updated to include the most recent submissions as well as additional historical submissions using the CBD's online reporting tool.

## UNCCD submissions

Our database includes a collection of submissions to the UN Convention on Combatting Desertification (UNCCD) including voluntary Land Degradation Neutrality Target commitments and reports and Drought Plans. These will be updated to include additional and the most up-to-date submissions as they are released on the UNCCD website, including country reports.

## Offshore Wind Reports

The POWER Library database includes hundreds of documents related to offshore wind globally, including industry reports, government policies, laws, strategies, and analyses from researchers and civil society. The documents in this library are curated by Ocean Energy Pathway.
