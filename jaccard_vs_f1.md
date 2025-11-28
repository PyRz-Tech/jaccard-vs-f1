# jaccard-vs-f1-wtf  
Why “overall accuracy” is sometimes the dumbest metric you can pick — and when it actually makes sense

Our goal when training models is to predict y from the features x.  
Well, most predictions come with a price tag — meaning how much damage a wrong prediction does: financial loss, someone’s life, trust, etc.

But in some problems, no, we only care about the quality and the percentage of correct predictions, and a mistake in certain places might not cost us anything at all.

This is exactly the point where we realize why we have to pick the right evaluation metric.

For example, in pixel-level classification (segmentation), we don’t care which class was confused with which — we only care how many percent of the pixels were predicted correctly so we can push that number higher.

But in disease detection, if the model wrongly says “healthy” while the person actually has the disease, someone might die. Here it suddenly matters a lot in which field the accuracy is high or low.

Two of our famous metrics are Jaccard and F1-score.  
Jaccard is exactly for the first case: only the overall correct percentage matters, where it went wrong doesn’t.  
F1-score is for the second case: it’s super important to us in which part the model screwed up.

That’s why before training any model we first have to sit down and think:  
If this model makes a mistake, what kind of damage and how bad will it be? Does that damage even matter to us or not?

This is exactly my view on Jaccard and F1-score.
---
[![Main Repo](https://img.shields.io/badge/Main_Repo-000000?style=flat&logo=github&logoColor=white)](README.md)
