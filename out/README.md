# out/

Outputs of `mental_health_label_agreement.ipynb`, one or more per step. With this folder in place the notebook reuses them, so no API calls or SVM training are needed to reproduce the results.

## Files

**Step 0 – Data**
- `items.csv`: the 103 rated posts (`statement_id`, `text`, original `user` label, length group `size`, `word_count`).

**Step 1 – Experts**
- `expert_labels.csv`: each expert's label per post, plus the two-rater (`cons2`) and three-rater (`cons3`) consensus.
- `agreement_experts.csv`: pairwise agreement and Cohen's κ among experts and with the original labels.

**Step 2 – LLMs**
- `llm_raw_<model>.jsonl`: every raw model response (three runs per post).
- `llm_scores_<model>.csv`: 0–10 scores per category, averaged over runs.
- `llm_labels.csv`: label per post and model.

**Step 3 – SVM**
- `svm_labels.csv`: labels predicted for the 103 posts by the SVM trained on the rest of the corpus.
- `svm_heldout.txt`: held-out accuracy and per-class report on a stratified 80/20 split.

**Step 4 – Agreement**
- `all_labels.csv`: all sources side by side.
- `agreement_overall.csv`: pairwise agreement and κ with bootstrap 95% CIs.
- `confusion_<ref>_vs_<source>.csv`: confusion matrices of Fig. 2.
- `topk_agreement.csv`: share of each source's labels within the experts' top-*k* categories.
- `reliability_alpha.csv`: Krippendorff's α, including each source added as a third rater.
- `agreement_cons3.csv`: agreement with the three-rater consensus.

**Step 5 – Length**
- `agreement_by_length.csv`: key contrasts for short, mid-length and long posts.

**Step 6 – Shortcut check**
- `shortcut.txt`: accuracy of the style-only classifier.
- `style_by_class.csv`: style features per class in the full corpus.

## Licence

The `statement` (post text) and `user_status` columns are taken from the [*Sentiment Analysis for Mental Health*](https://www.kaggle.com/datasets/suchintikasarkar/sentiment-analysis-for-mental-health) dataset by Suchintika Sarkar, released under the [ODbL v1.0](https://opendatacommons.org/licenses/odbl/1-0/) / [DbCL v1.0](https://opendatacommons.org/licenses/dbcl/1-0/) terms. That file is redistributed under the same licences. 

All other files are our own outputs, released under CC BY 4.0.
