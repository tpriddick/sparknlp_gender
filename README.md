# Exploring Gender Pronoun Distribution and Character Identification in 19th Century Novels

## Overview

`Exploring Gender Pronoun Distribution and Character Identification in 19th Century Novels` is a Natural Language Processing (NLP) project that analyzes gender representation in literary texts using SparkNLP and spaCy. The primary goal is to identify character genders in classic novels based on pronoun usage and to statistically analyze gendered language patterns within these texts.

## Project Motivation

This repository was created to explore:
- How reliably a character's gender can be predicted from the pronouns used in reference to them.
- Whether there is a statistically significant difference in the usage of male vs. female pronouns in works by female authors.

## Datasets

The corpus consists of three classic novels, all authored by women:
- *Pride and Prejudice* by Jane Austen
- *Frankenstein: Or, the Modern Prometheus* by Mary Shelley
- *Wuthering Heights* by Emily Brontë

Text data is sourced from Calvin's Project Gutenberg repository.

## Technologies Used

- **SparkNLP**: For part-of-speech tagging.
- **spaCy**: For Named Entity Recognition (NER), particularly identifying PERSON entities.
- **PySpark** and **Pandas**: Data handling and processing.
- **scipy.stats**: Statistical analysis.
- **matplotlib**: Data visualization.

## Methodology

1. **Corpus Preparation**: Books are cleaned for easier sentence splitting and pronoun analysis.
2. **Entity Recognition**: spaCy identifies PERSON entities in each sentence.
3. **Pronoun Counting**: For each person, male and female pronouns in the sentence are counted and attributed.
4. **Filtering**: Characters with fewer than 10 pronoun mentions are dropped.
5. **Gender Prediction**: Prediction for each character is based on whether male or female pronouns predominate.
6. **Manual Verification**: The `manual_verify` function allows user input to confirm or correct predicted genders.
7. **Accuracy Calculation**: Accuracy is measured overall and by gender for each book.
8. **Statistical Analysis**: Hypothesis tests are conducted to determine if differences in pronoun usage are significant.

## Hypotheses

1. There is no significant difference in the use of male vs. female pronouns in novels by female authors.
2. Character gender can be predicted from pronoun usage with better-than-chance accuracy.

## Example Usage

To run the analysis, use the included Jupyter notebook:

```python
# Install dependencies
%pip install sparknlp spacy pyspark

import sparknlp
import spacy
import pyspark
import pandas as pd
from sparknlp.pretrained import PretrainedPipeline

# Start SparkNLP session and load pipeline
spark = sparknlp.start()
pipeline = PretrainedPipeline("explain_document_ml")

# ...load and clean books, run analysis as demonstrated in nlp_pronouns.ipynb
```

## Results

- The model achieves varying accuracy by book and by gender.
- For instance, *Frankenstein* achieved 100% accuracy (possibly due to a small character set), while *Pride and Prejudice* and *Wuthering Heights* had lower but still substantial accuracy.
- Statistical tests suggest that differences in pronoun usage by gender may not be significant in these works.

## File Structure

- `README.md`: Project overview and instructions.
- `nlp_pronouns.ipynb`: Main notebook with code, methodology, and results.

## Getting Started

1. Clone the repository:
   ```
   git clone https://github.com/tpriddick/sparknlp_gender.git
   ```
2. Install dependencies (see above).
3. Open `nlp_pronouns.ipynb` in Jupyter and follow along.

## Team

- Tyler Gomez Riddick ([LinkedIn](https://www.linkedin.com/in/tyler-gomez-riddick/) | [Portfolio](https://www.datascienceportfol.io/tylergomezriddick))
- Cormac Dacker ([LinkedIn](https://www.linkedin.com/in/cormac-d/))
- Avery Pike ([LinkedIn](https://www.linkedin.com/in/averypike/))

## Contributing

Contributions, suggestions, and improvements are welcome. Please open an issue or submit a pull request.

## License

No license specified.

---

Project by [@tpriddick](https://github.com/tpriddick)
