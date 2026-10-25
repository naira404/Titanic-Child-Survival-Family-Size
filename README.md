### Experiment: Evaluating the Contribution of FamilySize

**Objective**

Investigate whether the engineered feature `FamilySize` improves the predictive performance of the Random Forest model for Titanic children.

**Hypothesis**

Since `FamilySize` is calculated as `SibSp + Parch + 1`, it may contain information already represented by the original family-related features. Removing it may therefore have little effect on model predictions.

**Experimental Setup**

- **Baseline model:** Random Forest using `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare`, `Embarked`, and `FamilySize`.
- **Alternative model:** The same Random Forest configuration without `FamilySize`.
- **Validation set:** The same 17 children were used to evaluate both models.
- **Evaluation metrics:** Accuracy, Precision, Recall, and F1-score.

**Results**

Both models achieved identical validation metrics:

| Metric | With FamilySize | Without FamilySize |
|---|---:|---:|
| Accuracy | 0.824 | 0.824 |
| Precision | 0.818 | 0.818 |
| Recall | 0.900 | 0.900 |
| F1-score | 0.857 | 0.857 |

Both models also produced identical predictions for all 17 validation examples.

**Interpretation**

Removing `FamilySize` did not change the observed validation performance or individual predictions in this experiment. One possible explanation is that `SibSp` and `Parch` already provide sufficient information for the fitted model to make the same decisions.

However, this experiment does not prove that `FamilySize` is universally useless. The validation set is small, and the result may differ with other data splits or samples.

**Limitations**

- Only 17 validation examples were evaluated.
- The validation set has already been used for model comparison.
- Identical predictions on this sample do not guarantee identical generalization performance.
- This experiment measures predictive behavior, not causal effects on survival.

**Conclusion**

For this particular train-validation split and model configuration, `FamilySize` did not change the model's predictions. Further evaluation across multiple data splits would be needed before drawing broader conclusions.
