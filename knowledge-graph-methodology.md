# Knowledge graph methodology

This section provides a deeper dive into the processes behind building our knowledge graph. If you’re looking for a high-level explanation, see our [FAQs](https://climate-laws.org/faq). Our methodology is open source – view our [GitHub repository](https://github.com/climatepolicyradar/knowledge-graph?tab=readme-ov-file).

## Our high-level goal

We aim to map key concepts in climate policy, the relationships between them, and their presence in climate policy and other related documents. This enables users to discover important topics, and identify connections between them. In the future, this database of connected knowledge will be used to improve our other applications like search and generative AI tools.

## Step 1: Identifying subject areas

Our team of climate policy experts are responsible for deciding which subjects in the climate policy domain are worth including in our knowledge graph. They prioritise concept development based on:

1. **User interest:** we regularly conduct user interviews to understand who our users are, and keep an eye on what people search for in our apps. If more users are interested in a topic, it becomes a higher priority for concept development.
2. **Policy relevance:** to develop classifiers that align with current policy priorities, we stay informed on climate policy discourse through expert interviews, research papers, news, industry conferences, and climate negotiations, among other sources. Our classifiers reflect current priorities while ensuring long-term relevance by focusing on enduring issues and integrating ongoing debates.
3. **Uniqueness:** taken together, the concepts allow users to explore the full breadth of climate policy discourse. Every additional concept is evaluated against the existing concepts. Concepts that bring a unique perspective are higher on the priority list.
4. **Prevalence in data:** concepts which occur frequently become a higher priority for concept development; there is little value in developing a classifier for concepts that are scarcely mentioned.
5. **Added value over search:** many terms are already easy to find with our regular search function, so we may prioritise topics that are difficult to find using simple keyword searches.

Of course, the criteria are sometimes at odds with each other. For example, impacted groups are not often mentioned in climate policy documents, but knowing how and where they *do* appear has a high level of policy relevance and user interest, so we’ve included them in our first public set of concepts.

## Step 2: Concept development

Once a subject area has been identified, we add a structured representation of it to our [concept store](https://climatepolicyradar.wikibase.cloud/wiki/Main_Page):

- Each concept is described by a set of labels which might be used to refer to it in text, a short description, a more comprehensive definition, and a set of references which support those claims.
- We then break concepts down into subconcepts e.g. our concept for “greenhouse gases” includes subconcepts like “CO₂”, “methane” and “fluorinated gases”. We also capture looser, more associative relationships between concepts concepts, like the relationship between “greenhouse gases” and “the greenhouse effect”.

We structure the concepts based on a large survey of existing literature, and conversations with third-party domain experts. To make our data interoperable with other projects, we use existing concept vocabularies or taxonomies wherever possible. Sometimes, the existing structure of the concept store means that minor adjustments need to be made to new taxonomies as they’re incorporated; For example, the same concepts can appear in multiple taxonomies. In those cases, we endeavour to capture both perspectives, including the subconcepts and relationships from both source taxonomies.

Our concepts are stored in a [Wikibase](https://wikiba.se/) instance, the same technology which powers [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page). As the structured data backbone of Wikipedia and countless other projects, Wikidata has proven its ability to represent complex, open, interconnected knowledge at a global scale. This choice also allows us to build on a proven set of community-driven best practices for editors.

## Step 3: Classifier development

For each concept, our data science team creates create a classifier using:

- **Simple keyword-based matchers:** we use these when when concepts are described by a set of clear, unambiguous terms.
- **More advanced AI models:** these vary in size, from [BERT](https://en.wikipedia.org/wiki/BERT_(language_model))-sized models to optimised prompts for third-party [large language models](https://en.wikipedia.org/wiki/Large_language_model). We use these for nuanced topics which require more contextual understanding (e.g., differentiating between policies which mention adding climate finance subsidies, or removing them).

In cases where performance is equivalent, we’ll always choose to use smaller, simpler models. Their results are typically easier to interpret and explain, and each prediction uses less energy, which keeps costs down and minimises the negative climate impacts of our work.

## Step 4: Evaluation

Each classifier is tested against human-labelled data to measure accuracy. Our evaluation includes qualitative and quantitative checks:

- **Quantitative metrics:** for each concept, our policy team manually label mentions of the concept in real passages, sampled carefully to provide a balanced dataset across countries, document types, and languages.
We then ask the classifier to make predictions about *the same set of passages*, and count the instances where the humans and machines agree or disagree. The comparison with expert judgements allows us to compare classifier performance quantitatively.
- **Quality assurance:** before the classifier results are shown to real users, we review a sample to ensure that the results feel right.

You can read more detail on each of these steps in the sections below.

### **Sampling**

Without existing benchmarks, the power of our evaluation approach depends upon the diversity of the passages we can sample from our dataset.

While concepts appear all over our corpus, mentions of a *specific* concept are almost always sparse. For example, if we sampled 100 sentences from our dataset at random, we would be very unlikely to find any positive matches for a given concept, and a dataset with no mentions is unhelpful for evaluating our classifiers! In other words, fully random sampling would give robust results in theory, but is unworkable in practice as the number of passages we would need to manually label is simply too large.

We therefore take a diverse but non-random sample of passages: a few which obviously mention the concept, a few where it definitely doesn’t appear, and a range of ambiguous cases in between. Being able to compare our machine predictions to human experts’ on all of these ambiguous cases gives us the best chance of improving the classifier in each round of experimentation.

More concretely, we combine:

- passages taken randomly from our dataset (probably not matches)
- passages based on the concept’s labels (probably matches), and
- passages based on the [embedding](https://en.wikipedia.org/wiki/Sentence_embedding) similarity of a concept (likely to sit around that fuzzy, ambiguous semantic boundary of the concept).

We also try to ensure our classifiers perform just as well for each group that is represented or affected by the documents in our dataset. We know that the data itself is imbalanced: Some countries publish many climate policies, while some of the most vulnerable countries publish far fewer. Some non-English-language documents go through a machine-translation process which could affect the quality of our results. We also collect a wide array of document types (policy, corporate disclosures, litigation, and international funding agreements, among others), each of which can describe the same concepts using different language.

In an effort to rebalance and ensure equity in the quality of our predictions, we’ve sampled our evaluation sets as evenly as possible from each world bank region, document type, and from translated and non-translated documents. Before the results of a classifier are shown to users, we validate that its performance is consistent across each of these sub-groups.

### Vibe checks

The calculation of quantitative metrics described above gives us a useful indicator of how our classifiers perform. However, our team of policy experts is small, and the limitations on time mean that our evaluation datasets are too small to provide absolute statistical certainty.

In addition to verifying that the quantitative metrics meet our thresholds for quality, we also run a “vibe check” of the classifiers’ predictions before releasing them to the public. Even if the quantitative metrics suggest that a classifier is performing well, if the predictions that we see across the whole dataset don’t reflect the research that the policy team did, we won’t publish the results.

## Further experiments

We’re proud of our first set of classifiers, but this is only beginning. Here are a few things we are working on:

- New classifier architectures for improved accuracy – with more capacity for labelling, we could use the expert annotations to train supervised models as well as evaluating them. New types of classifier (or combinations thereof) should allow us to classify more nuanced concepts, including ones where our current approaches haven’t passed the vibe check.
- Expansion of our concept database – we are continuously cataloguing new concepts, covering new areas of the climate policy landscape. Our knowledge graph should become more richly connected, allowing you to answer more sophisticated questions with it.
- Integration with search and AI-driven tools – the knowledge graph is a new pillar in our technology stack which we hope will integrate with many new and existing features. For example, results from our search engine could be populated with relevant concepts. Our upcoming generative-AI features (e.g. [Queried](https://queried.labs.climatepolicyradar.org/), our RAG prototype) are also likely to benefit from the grounded expertise in our concept store.
- Better sampling methods for fairer evaluation – we’re working on new ways of sampling our concepts’ evaluation datasets to deliver more meaningful and equitable metrics.
- Improving the quality of machine-readable text – if we can’t accurately extract text from a document, we won’t be able to find concepts within it. We’re actively working to improve this across the board.
