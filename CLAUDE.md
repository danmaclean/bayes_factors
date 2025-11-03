# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Quarto book project titled "Bayesian Inference with Bayes Factors" by Dan MacLean. The book teaches Bayesian statistical methods as an alternative to frequentist statistics, focusing on using Bayes Factors for hypothesis comparison. The content includes theoretical background and practical R implementations using the `BayesFactor` package.

## Build and Development Commands

### Building the Book

```bash
# Render the entire book to HTML and PDF
quarto render

# Preview the book with live reload
quarto preview

# Render to specific format
quarto render --to html
quarto render --to pdf
```

### Managing R Dependencies

This project uses `renv` for R package management:

```bash
# In R console - restore package environment
renv::restore()

# Update packages
renv::update()

# Capture current package state
renv::snapshot()
```

The `.Rprofile` automatically activates the renv environment.

## Project Structure

### Configuration Files

- `_quarto.yml`: Main Quarto configuration defining book structure, chapters, output formats (HTML with cosmo theme, PDF), and bibliography settings
- `_bookdown.yml`: Legacy bookdown configuration (project appears to have migrated from bookdown to Quarto)
- `renv.lock`: R package dependencies lock file

### Content Organization

The book follows a structured chapter system defined in `_quarto.yml`:

1. **index.qmd**: Motivation and introduction explaining the limitations of p-values and benefits of Bayesian inference
2. **Background section**:
   - `bayes_factor_intro.qmd`: Core concepts of Frequentist vs Bayesian probability and Bayes Theorem
3. **Tests with Bayes Factors section**:
   - `bayes_t.qmd`: Bayes Factor t-tests for two-sample comparisons
   - `bayes_anova.qmd`: ANOVA using Bayes Factors
   - `bayes_proportion.qmd`: Proportion tests with Bayes Factors
4. **Appendices**:
   - `prerequisites.qmd`: Prerequisites
   - `r-fundamentals.qmd`: R fundamentals

### Output

- All rendered output goes to `docs/` directory (configured in both YAML files)
- This supports GitHub Pages deployment from docs folder

## Book Architecture

The book demonstrates Bayesian statistical methods through:

1. Philosophical foundation: Contrasting frequentist and Bayesian interpretations of probability
2. Practical implementation: Using R's `BayesFactor` package for common statistical tests
3. Pedagogical approach: Each chapter includes Questions, Objectives, and Keypoints sections
4. Code examples: Executable R code blocks demonstrating real analyses (e.g., PlantGrowth dataset)

## Working with Content

### Adding New Chapters

1. Create new `.qmd` file
2. Add to the `chapters` or `appendices` list in `_quarto.yml`
3. Follow existing chapter structure with Questions/Objectives/Keypoints

### Bibliography

- `book.bib`: Main bibliography file
- `packages.bib`: R packages bibliography
- Both are referenced via `bibliography: book.bib` in `_quarto.yml`

## Important Notes

- The project has migrated from bookdown to Quarto (both config files present)
- The `_bookdown.yml` references `.Rmd` files while the project now uses `.qmd` files
- Output directory is consistently set to `docs/` for web publishing
- The book emphasizes moving away from p-values toward evidence-based Bayesian hypothesis comparison