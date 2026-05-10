# DRL Meets LLM: Sentiment-Aware Crypto Trading Literature Review

This repository contains a customized SurVis literature browser for the topic:

**DRL meets LLM: Literature Review on Sentiment-Aware Crypto Trading**

It is prepared for **COMP4126 Research Methods - Coursework 3** and presents a curated BibTeX collection covering deep reinforcement learning, large language models, sentiment analysis, cryptocurrency trading, and related financial-market studies.

## Preview

Start a local static server from the project root:

```bash
python3 -m http.server 8001 --bind 127.0.0.1 --directory src
```

Then open:

```text
http://127.0.0.1:8001/
```

If the page still shows an older layout after editing files, force refresh the browser:

```text
Cmd + Shift + R
```

## Project Structure

```text
bib/references.bib                 Main BibTeX source file
src/index.html                     SurVis entry page
src/properties.js                  Page title, subtitle, visible tag clouds, custom theme
src/styles/drl_llm_theme.css       Custom simplified visual theme
src/data/tag_categories.js         Tag groups shown in the filter panel
src/data/authorized_tags.js        Tag display names and tooltip descriptions
src/data/generated/bib.js          Generated bibliography data used by SurVis
update_data.py                     Script for regenerating SurVis data from BibTeX
```

SurVis reads the generated file `src/data/generated/bib.js` in the browser. After changing `bib/references.bib`, regenerate or manually sync the generated data before refreshing the page.

## Updating References

Add or edit papers in:

```text
bib/references.bib
```

Each entry should include a `keywords` field with three categories:

```bibtex
keywords = {method:DRL, method:Sentiment, domain:Cryptocurrency,type:Journal}
```

Required tag categories:

```text
method:  Main method or research approach
domain:  Market or asset class
type:    Publication type or venue
```

Current examples:

```text
method:DRL
method:LLM
method:Sentiment
method:Traditional-NLP
method:Review

domain:Cryptocurrency
domain:Stock

type:Journal
type:IEEE
type:Book
type:Survey
```

Avoid missing category tags, because SurVis will otherwise create `?` filter labels.

## Regenerating Data

Run:

```bash
python3 update_data.py
```

The script watches `bib/references.bib` and updates:

```text
src/data/generated/bib.js
src/data/generated/available_pdf.js
src/data/generated/available_img.js
```

Stop it with `Ctrl + C` when finished.

## Customization Notes

Page metadata is configured in:

```text
src/properties.js
```

The current page title is:

```text
DRL meets LLM: Literature Review on Sentiment-Aware Crypto Trading
```

The custom theme is loaded through:

```js
var customStyle = 'styles/drl_llm_theme.css';
```

Tag group labels and descriptions are configured in:

```text
src/data/tag_categories.js
src/data/authorized_tags.js
```

Use these files to keep the filter panel readable and consistent.

## About SurVis

This project is based on SurVis, a visual literature browser for presenting and exploring scientific reference collections.

Original SurVis project:

```text
https://github.com/fabian-beck/survis
```
