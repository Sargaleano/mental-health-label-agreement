# data/

- `ratings_KYG82_….csv`, `ratings_VPR17_….csv`, `ratings_NEL81_….csv`: 0–10 scores per category given by three clinical psychologists to the same 103 posts, blind to the original label. Raters are identified by code only. `statement_id` is the row id (`Unnamed: 0`) of `Combined Data.csv` in the Kaggle corpus.
- The Kaggle corpus itself is not redistributed. Download `sentiment-analysis-for-mental-health.zip` from https://www.kaggle.com/datasets/suchintikasarkar/sentiment-analysis-for-mental-health and place it here.

## Note on the `p_*` and `expert_status` columns

These columns were written by the rating tool at collection time (softmax of the scores and its argmax). They are **not used** in the analysis: when all scores are zero or the top score is tied, the argmax silently returns the first category (*Anxiety*). The analysis notebook recomputes each rater's label from the raw 0–10 scores and leaves such posts unlabelled. The rating tool presented the seven category sliders in random order for each post.

## Licence

The `statement` (post text) and `user_status` columns are taken from the *Sentiment Analysis for Mental Health* dataset by Suchintika Sarkar (https://www.kaggle.com/datasets/suchintikasarkar/sentiment-analysis-for-mental-health), available under the Open Database License (ODbL v1.0, https://opendatacommons.org/licenses/odbl/1-0/) with contents under the Database Contents License (DbCL v1.0, https://opendatacommons.org/licenses/dbcl/1-0/). These files are redistributed under the same terms. 

The expert ratings were collected for this study and are released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
