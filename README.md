# Philippine Industrial Taxonomy: Quantifying Structural Vulnerability

Philippine industrial policy is blind. By grouping 99.5% of businesses under a single "MSME" label, the state treats a scalable tech startup and a subsistence bakery as identical entities. This repository provides a data-driven correction: a new industrial taxonomy constructed via K-Means clustering of 228 three-digit PSIC industries.

## The Problem: Policy Homogeneity
The "Missing Middle" in the Philippines is not just a productivity gap but a structural failure. Traditional classifications group firms by output (what they make) rather than structure (how they operate). This masks latent fragility, leading to "one-size-fits-all" interventions that fail to reach the most vulnerable sectors.

## The Solution: A Data-Driven Taxonomy
Using 2021 PSA establishment data, we engineered a "structural fingerprint" for each industry based on:
1. **Average Firm Size**: A proxy for scale.
2. **SME Density**: Measuring the presence of the "Missing Middle."
3. **Large-Firm Density**: Indicating industrial concentration.

### Four Economic Archetypes
Our K-Means model ($k=4$) identifies four distinct structural groups:
*   **The Survivalist**: Hyper-fragile micro-firms (avg. 10 employees) in a structural monoculture.
*   **The Middle**: The engines of growth, structurally distinct from survivalists but lacking scale.
*   **The Transition**: High-entropy industries successfully graduating to larger scales.
*   **The Oligopoly**: Capital-intensive apex sectors, independent of local credit constraints.

## Key Findings
*   **Structure Predicts Failure**: Regression analysis shows that the share of "Survivalist" industries within a sector is a robust predictor of pandemic-era business closures ($r = 0.44$).
*   **Regional Risk**: Peripheral regions like Zamboanga Peninsula exhibit significantly higher structural vulnerability compared to urban hubs like the NCR.
*   **The Survivalist Trap**: Once a sector crosses 80% micro-density, average firm size hits a "glass ceiling," preventing graduation to formal SME status.

## Repository Structure
*   `main.ipynb`: Full end-to-end data pipeline, clustering model, and visualization suite.
*   `main.pdf`: The complete research paper detailing the econometric methodology (available at root for convenience).
*   `data/`: PSA 2021 source datasets (Employment, Establishments, Closures).
*   `images/`: High-resolution figures used in the paper.
*   `paper/`: LaTeX source documents, ACM stylesheets, and configuration files for compiling the paper.

## Requirements
This project uses `uv` for dependency management. To reproduce the analysis:
```bash
uv pip install -r requirements.txt
jupyter nbconvert --to notebook --execute main.ipynb
```

## Authors
*   Precious Mae Mercado Divina (DLSU)
*   Gheann Christie Mediodia Cuevas (DLSU)
*   Aaron Joshua Estacio Sison (DLSU)
