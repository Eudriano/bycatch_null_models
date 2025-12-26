# Manuscript

## *Seasonal dynamics of functional diversity in a trawl bycatch assemblage: A null-model approach reveals stochastic assembly on a shifting baseline*

### Costa et al. (2025)

---

## **Script 1: null-model: observed seasonal patterns vs random assembly expectations**

This script implements a comprehensive null-model analysis to test whether observed seasonal patterns of functional diversity (**FRic, FEve, FDiv**) deviate from random assembly expectations. Using a permutation framework, it maintains observed species richness and abundance distributions while randomizing species identities and trait-abundance relationships from the regional pool. For each season, it generates 999 null communities, calculates their functional diversity metrics, and compares them to observed values via Standardized Effect Sizes (SES) and exact permutation-based *p*-values.

**Key Features:**
- Permutation-based null models with 999 iterations per season
- Maintains observed richness and abundance distributions
- Calculates SES scores and exact *p*-values
- Tests H₀: Observed FD = Expected FD from random assembly

---

## **Script 2: comparing seasonal null-model expectations**

This script provides the final analysis and visualization for the functional diversity study, comparing seasonal null-model expectations across the three key metrics. It generates a publication-ready statistical table (**Table 1**) with pairwise seasonal contrasts—including effect sizes, bootstrap confidence intervals, and adjusted *p*-values—and a complementary multi-panel figure (**Figure A‑C**) that visually summarizes the differences using half-eye density plots. Built for independent seasonal simulations, the analysis ensures appropriate inference and clear communication of results for formal publication.

**Key Outputs:**
- **Table 1**: Pairwise seasonal contrasts with effect sizes, bootstrap CIs, and adjusted *p*-values
- **Figure A-C**: Half-eye density plots of Δ draws from independent null distributions
- Multiplicity correction (Holm method) across 18 tests

---

## **Script 3: Paired Pairwise Analysis**

This script performs a rigorous paired pairwise analysis comparing observed seasonal differences in functional diversity to their null expectations. Unlike independent designs, this approach respects the inherent correlation structure of the simulation framework by computing seasonal differences *within each common simulation ID*, ensuring proper alignment of null distributions. For each of the three metrics across six seasonal comparisons, it calculates effect sizes, exact permutation-based *p*-values, and applies Holm multiplicity correction.

**Key Distinction:**
- **Paired design**: Δ differences computed within each simulation (by Simulation ID)
- Appropriate when null seasons share correlation structure
- Accounts for within-simulation variability

---

## **Methodological Comparison**

| Aspect | Script 1 (Null Model) | Script 2 (Independent) | Script 3 (Paired) |
|--------|-----------------------|------------------------|-------------------|
| **Design** | Single-season null models | Independent seasonal comparisons | Paired seasonal comparisons |
| **Purpose** | Test if observed ≠ random | Compare seasons independently | Compare seasons with paired structure |
| **Key Assumption** | Seasons independent | Seasons independently simulated | Seasons share simulation structure |
| **Statistical Test** | SES & permutation test | Bootstrap CI & adjusted *p*-values | Paired permutation test |


---

## **Key Figures**

### **Figure 5: Comparison of Observed Functional Diversity to Null Model Expectations**

![Figure 5: Comparison of observed functional diversity metrics to null model expectations](https://github.com/user-attachments/assets/1f48af4f-733b-4d0d-ad94-466eaaba2069)

**Description:** Comparison of observed functional diversity metrics to null model expectations across seasons: (A) functional richness (FRic), (B) functional evenness (FEve), and (C) functional divergence (FDiv). Observed values (points) are compared against the distribution of null model expectations for each season.

### **Figure 6: Pairwise Seasonal Differences in Null Expectations**

![Figure 6: Pairwise seasonal differences in null expectations of functional diversity](https://github.com/user-attachments/assets/ebbbc421-eb23-4307-8ad5-60d96f4610cb)

**Description:** Pairwise seasonal differences in null expectations of functional diversity. Panels show (A) FRic, (B) FEve, and (C) FDiv. For each seasonal contrast:

- **Half‑eye density:** Distribution of null contrasts (Δ = Nullₛ₂ - Nullₛ₁) from independent draws
- **Black point:** Mean null contrast (Δ̄)
- **Black segment:** Interquartile range (IQR; 25th–75th percentiles)
- **Green segment:** 95% bootstrap confidence interval for Δ̄
- **Dashed line:** Δ = 0 (no difference)
- **Labels:** Cohen's *d*<sub>pooled</sub> with magnitude interpretation:
  - Negligible (|d| < 0.2)
  - Small (0.2 ≤ |d| < 0.5)
  - Medium (0.5 ≤ |d| < 0.8)
  - Large (0.8 ≤ |d| < 1.3)
  - Very large (|d| ≥ 1.3)

---

All scripts are implemented in R and designed for reproducible ecological analysis of functional diversity patterns.
