# Gradient Boosting Lab

An interactive study guide for §18.5.5–18.6 of Kevin P. Murphy, *Probabilistic Machine Learning: An Introduction*
(gradient boosting, gradient tree boosting, XGBoost, feature importance and partial dependence plots).

Every section has an **Explain it** box at four levels (Kid, High school, Undergrad, Grad / MLE), switchable globally from the top bar.

- **18.5.5 Gradient boosting:** Table 18.1 as curves (loss and negative gradient for squared, absolute, Huber, exponential, binary and multiclass log loss). Then gradient descent on 60 points two ways: raw functional gradient steps with a line search (Eqs. 18.38–18.40), which fit the training points and never generalize, and Algorithm 18.3, which fits a tree to the pseudo-residuals. Toggle outliers to see squared loss chase them and absolute/Huber loss ignore them.
- **Classification and subsampling:** BinomialBoost (one tree per round) and 3-class softmax boosting (Eqs. 18.42–18.43) on a noisy spiral, with the pseudo-residual map I(y = c) − π_c and test log loss with and without stochastic subsampling.
- **18.5.5.1 Gradient tree boosting:** the same regions with two kinds of leaf values. Least-squares leaves from the pseudo-residuals vs leaves re-solved for the loss (Eq. 18.45: mean, median, Huber step), with test error curves.
- **18.5.5.2 XGBoost:** drag a threshold and read G, H, w* = −G/(H + λ) and the split gain (Eq. 18.56) under log or squared loss; then grow a whole tree and watch λ shrink leaf weights and γ remove splits.
- **18.6.1 Feature importance:** a boosted classifier on spam-like data (gain importance, Eqs. 18.57–18.58, vs permutation importance) and a random forest on drawn 0s and 8s with a pixel-importance map averaged over 1, 10 or 60 trees (Fig. 18.8).
- **18.6.2 Partial dependence:** 1-D PD plots with deciles, ICE curves and the true model's PD, plus the hp × ! 2-D PD (Fig. 18.10b) with slices that show the interaction.
- A 44-question quiz tagged by level and a cheat sheet.

Single self-contained `index.html`, no build step. Loads Google Fonts and MathJax from cdnjs. All data are synthetic and generated in the page from fixed seeds. The spam set only borrows feature names from the HP spam data, and its labels come from a known logistic model (with an "!" × "hp" interaction), so the page can show the true partial dependence. Every tree, boosted model and forest is fit live in the browser.
