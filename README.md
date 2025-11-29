# Golf Tourism Belek–Algarve UGC Noun Phrase Metrics

This repository contains noun phrase (NP) metrics derived from an academic study on the competitive positioning of two golf tourism destinations: **Belek (Turkey)** and **Algarve (Portugal)**.

The data are **aggregated outputs** obtained from TripAdvisor hotel reviews (English interface, 2013–2025) and are intended to support **reproducible research** on golf tourism, destination competitiveness, and text analytics.  
No raw review texts are shared in order to respect platform terms of use; only derived NP-level statistics are provided.

---

## Data Description

### `np_metrics_belek_algarve.csv`

Each row corresponds to a single **noun phrase** (NP) extracted from user reviews. The main columns are:

- `phrase` – Canonical noun phrase (lemmatised and normalised, e.g. `excellent service`, `golf course`).
- `df_Belek`, `df_Algarve` – Document frequency: number of distinct reviews in which the NP appears in Belek / Algarve.
- `df_total` – Total document frequency across both destinations.
- `prev_Belek`, `prev_Algarve` – Prevalence of the NP in each destination  
  (NP reviews / total reviews for that destination).
- `logodds_B_vs_A`, `z_B_vs_A` – Monroe et al. (2008) informative log-odds and z-score  
  (> 0 ⇒ more typical for Belek, < 0 ⇒ more typical for Algarve).
- `lift_Belek`, `lift_Algarve` – **Rating lift**: difference in average rating between reviews  
  that mention the NP and those that do not, computed separately for each destination.
- `with_B`, `without_B`, `with_A`, `without_A` – Number of reviews with / without the NP  
  used in the lift calculations.

The same NP extraction and scoring framework is also applied to the **golf-related subset** of reviews (flagged using a domain-specific golf dictionary), enabling focused analysis of golf-specific attributes such as course conditions, practice facilities, tee times, and pricing.

---

## Methodological Summary

- **Data source:** TripAdvisor hotel reviews for Belek and Algarve, 2013–2025 (English only).
- **Preprocessing:** Tokenisation, stop-word removal, lemmatisation, and domain-specific stop-list
  (hotel names, destination names, overly generic terms).
- **NP extraction:** Rule-based patterns using the [`spaCy`](https://spacy.io/) Matcher
  to capture adjectival and prepositional noun phrases (e.g. *great food*, *view of the sea*).
- **Scoring:**
  - Prevalence by destination.
  - Distinctiveness using informative log-odds and z-scores (Monroe et al., 2008).
  - Rating lift based on differences in average user rating.

These metrics were used in the article to identify:
- Belek-typical and Algarve-typical concepts,
- Shared but high-impact service attributes,
- NP-level drivers and detractors of satisfaction for golf and non-golf experiences.

---

## Academic Use and Citation

If you use these data or code in academic work, please cite the associated article:

> Büyükeke, A. (20XX). *Understanding Golf Tourism Competitiveness: Evidence from Belek and Algarve*. [Journal name], [volume(issue)], [pages].  

(Replace with the final bibliographic information once the paper is published.)

You may also reference this repository as:

> Büyükeke, A. (20XX). *Golf tourism Belek–Algarve UGC NP metrics* (Version 1.0) [Data set]. GitHub. \<GitHub URL\>

---

## Contact

For questions about the dataset or the underlying methodology, please contact:

**Ahmet Büyükeke**  
Adana Alparslan Türkeş Science and Technology University  
Department of Management Information Systems  

