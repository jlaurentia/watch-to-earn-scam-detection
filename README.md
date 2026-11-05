# Watch-to-Earn Scam Detection in Indonesian Google Play Reviews

## Overview

This repository contains an annotated dataset of Indonesian Google Play reviews collected from watch-to-earn applications. The dataset was developed to support research on detecting potential scam-related experiences and identifying behavioral scam indicators using BERT-based language models.

The research compares four pretrained transformer-based models: multilingual BERT (mBERT), IndoBERT, DistilBERT, and XLM-RoBERTa, across two classification tasks.

## Dataset Description

The dataset consists of **19,336 unique Indonesian Google Play reviews** collected from 15 watch-to-earn applications, including Melolo, Free Reels, and Drama Wave.

A total of 19,354 reviews were initially collected. After removing 18 duplicate reviews, 19,336 unique reviews remained.

The dataset is divided into two classification tasks:

### Level 1: Binary Scam Detection

**File:** `level1_reviews_text_labels.csv`

This dataset contains 19,336 reviews classified into two categories:

| Label | Description | Number of Reviews |
|---|---|---:|
| Non-Scam | Reviews without identified scam-related indicators | 14,361 |
| Scam | Reviews describing potential deceptive earning mechanisms or scam-related experiences | 4,975 |
| **Total** | | **19,336** |

### Level 2: Behavioral Scam Indicator Classification

**File:** `level2_scam_indicators_text_labels.csv`

This dataset contains 4,975 reviews labeled as Scam at Level 1. Each review is assigned one primary behavioral indicator.

| Label | Description | Number of Reviews |
|---|---|---:|
| Reward Promise (RP) | Misleading or unfulfilled promised earnings | 1,539 |
| Withdrawal Problem (WP) | Difficulties withdrawing accumulated rewards | 2,983 |
| Deposit Request (DP) | Requests for payments, deposits, or top-ups | 242 |
| Invite Others (IO) | Recruitment requirements for obtaining rewards or completing withdrawals | 211 |
| **Total** | | **4,975** |

## Dataset Structure

Both CSV files contain the following columns:

| Column | Description |
|---|---|
| `review_id` | Unique identifier for each review |
| `review_text` | Original user review text |
| `label` | Assigned classification label |

The datasets use text-based labels for readability. The `review_id` field allows reviews in Level 2 to be associated with their corresponding records in Level 1.

## Data Annotation

The reviews were manually annotated by three independent annotators using predefined annotation guidelines.

Final labels were determined through majority voting.

The annotation process consisted of two stages:

1. **Level 1:** Identification of Scam and Non-Scam reviews.
2. **Level 2:** Classification of Scam reviews into one of four behavioral indicators.

The labels represent potential scam-related experiences reported by users and should not be interpreted as definitive evidence that an application is fraudulent.

## Data Preprocessing

The following preprocessing procedures were applied:

- Conversion of review content into string format.
- Removal of URLs.
- Normalization of excessive whitespace.
- Removal of duplicate reviews based on identical cleaned text.

Stemming, stopword removal, and punctuation removal were not applied to preserve contextual information in the original reviews.

## Research Methodology

The dataset was used to evaluate four pretrained transformer-based language models:

- mBERT
- IndoBERT
- DistilBERT
- XLM-RoBERTa

The experiments used stratified training, validation, and testing splits of 70%, 15%, and 15%, respectively, with a random seed of 42.

Both classification levels were trained and evaluated independently. End-to-end pipeline performance was not evaluated.

## Intended Use

This dataset is intended for academic research in:

- Indonesian natural language processing.
- Scam and fraud-related text classification.
- Behavioral scam indicator identification.
- Consumer protection and cybersecurity research.

The dataset should not be used as the sole basis for determining whether an application or its developer has committed fraud.

## Data Source

The dataset was collected from user reviews of 15 applications available on Google Play:

1. Bling story
2. Free Reels
3. Snack Video
4. Melolo
5. Drama Wave
6. Story Blast
7. Snap Dramas
8. Short Max
9. Fomi
10. Cash Drama
11. Inbox Dollar
12. Lucky Money Cash
13. Star Short
14. Gold Drama
15. Tik Cash

The source data were collected through Google Play review scraping. Following data preparation, duplicate removal, and manual annotation, the final research dataset contains 19,336 unique reviews.

The dataset is provided for research on potential scam-related experiences and behavioral indicators in Indonesian application reviews.

## Contact

For research-related questions, please contact the corresponding author through the contact information provided in the associated publication.
