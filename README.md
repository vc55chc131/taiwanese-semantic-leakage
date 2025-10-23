# taiwanese-semantic-leakage
Untranslatables in Taiwanese: A Corpus-Based Study of Semantic Leakage in AI Translations
# Taiwanese Semantic Leakage in AI Translations

This repository contains all data, code, and materials used in the study "Untranslatables in Taiwanese: A Corpus-Based Study of Semantic Leakage in AI Translations" published in the Journal of Translation Studies.

## Repository Structure

- **corpus/**: The complete corpus of 26,046 Taiwanese sentences with translations and back-translations
  - `taiwanese_corpus_with_translations.xlsx`: Main corpus file with original Taiwanese sentences and Mandarin translations
  - `taiwanese_backtranslation_corpus.xlsx`: Corpus with back-translations from Mandarin to Taiwanese

- **dictionary/**: Custom dictionaries for text processing
  - `taiwanese_custom_dictionary.txt`: Custom Taiwanese dictionary used with Jieba for word segmentation

- **prompts/**: Templates and parameters used for AI translation
  - `translation_prompts.md`: All prompt templates used for translation and back-translation
  - Contains API parameters used with GPT-4O

- **benchmarks/**: Test sets and benchmark results
  - `benchmark_results.md`: Detailed benchmark results comparing GPT-4O with specialized systems and human translators

- **analysis/**: Scripts for analyzing translations and calculating metrics
  - `calculate_sli.py`: Python script for calculating Semantic Leakage Index (SLI)
  - `correlation_analysis.txt`: Correlation analysis results with Holm-Bonferroni correction
  - `code_reproducing_analysis.txt`: Additional code for reproducing analysis results

- **data/**: Raw data for figures and tables
  - Contains CSV files and source data for all figures and tables in the paper

## How to Reproduce the Results

### Prerequisites

- Python 3.8 or higher
- Required Python packages:
  - pandas
  - numpy
  - scipy
  - jieba
  - scikit-learn
  - sentence-transformers
  - matplotlib
  - seaborn
  - openpyxl

Install all required packages:

```bash
pip install pandas numpy scipy jieba scikit-learn sentence-transformers matplotlib seaborn openpyxl
```

### Step 1: Calculate Semantic Leakage Index (SLI)

```bash
python analysis/calculate_sli.py --input corpus/taiwanese_corpus_with_translations.xlsx --output data/sli_results.csv --dict dictionary/taiwanese_custom_dictionary.txt --visualize
```

This will:
1. Load the corpus with original Taiwanese sentences, Mandarin translations, and back-translations
2. Calculate the SLI for each sentence pair
3. Generate visualizations in the `data/figures` directory

### Step 2: Analyze Correlations

The correlation analysis results are provided in `analysis/correlation_analysis.txt`. To reproduce these results:

```bash
python analysis/calculate_correlations.py --input data/sli_results.csv --output data/correlation_results.csv
```

### Step 3: Run Benchmark Tests

Benchmark results are provided in `benchmarks/benchmark_results.md`. The test sets used for benchmarking are included in the corpus files.

## Data Availability

All data used in this study is available in this repository and has been archived on Dataverse: https://doi.org/10.7910/DVN/0WM6HO

## Citation

If you use this data or code in your research, please cite:

```
Author, A. (2025). Untranslatables in Taiwanese: A Corpus-Based Study of Semantic Leakage in AI Translations. Journal of Translation Studies, Vol. X, pp. XX-XX.
```

## License

This repository is licensed under the MIT License - see the LICENSE file for details.

## Contact

For questions about the data or code, please contact the authors at author@university.edu.
