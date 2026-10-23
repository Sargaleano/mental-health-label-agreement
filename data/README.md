# data/

- `ratings_KYG82_…_repaired.csv`, `ratings_VPR17_….csv`, `ratings_NEL81_….csv`: 0–10 scores per category given by three clinical psychologists to the same 103 posts, blind to the original label. Raters are identified by code only. `statement_id` is the row id (`Unnamed: 0`) of `Combined Data.csv` in the Kaggle corpus.
- The Kaggle corpus itself is not redistributed. Download `sentiment-analysis-for-mental-health.zip` from https://www.kaggle.com/datasets/suchintikasarkar/sentiment-analysis-for-mental-health and place it here.

## Note on the `p_*` and `expert_status` columns

These columns were written by the rating tool at collection time (softmax of the scores and its argmax). They are **not used** in the analysis: when all scores are zero or the top score is tied, the argmax silently returns the first category (*Anxiety*). The analysis notebook recomputes each rater's label from the raw 0–10 scores and leaves such posts unlabelled. The rating tool presented the seven category sliders in random order for each post.
