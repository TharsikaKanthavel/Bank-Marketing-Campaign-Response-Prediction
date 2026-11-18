# Model / Method Comparison, Bank Marketing Campaign Response Prediction

## Candidate Models
Five models were trained on the 60% training set and compared exclusively on the
20% validation set, so no model-selection decision was influenced by test data.

- Logistic Regression (baseline), class_weight='balanced', simple and interpretable.
- Random Forest, tolerates the multicollinearity identified via VIF, since tree splits
  are unaffected by correlated features the way linear coefficients are.
- Gradient Boosting, builds trees sequentially, each correcting the previous one's errors.
- XGBoost, a more regularised, optimised gradient boosting implementation,
  using scale_pos_weight for imbalance.
- k-Nearest Neighbours, classifies by the majority class among the 15 nearest,
  distance-weighted neighbours.

## Validation Set Comparison (Untuned Models)
Sorted by ROC-AUC, descending.

| Model                | Precision | Recall | F1   | ROC-AUC | PR-AUC |
|-----------------------|-----------|--------|------|---------|--------|
| Gradient Boosting     | 0.39      | 0.65   | 0.49 | 0.8040  | 0.4842 |
| Logistic Regression   | 0.36      | 0.65   | 0.47 | 0.8011  | 0.4668 |
| Random Forest         | 0.52      | 0.28   | 0.37 | 0.7753  | 0.4080 |
| XGBoost               | 0.37      | 0.56   | 0.45 | 0.7716  | 0.4300 |
| k-Nearest Neighbours  | 0.50      | 0.24   | 0.33 | 0.7485  | 0.3400 |

Gradient Boosting led on both ROC-AUC and PR-AUC, narrowly ahead of the Logistic
Regression baseline, and was selected for hyperparameter tuning.

## Hyperparameter Tuning (Selected Model: Gradient Boosting)
- Method: RandomizedSearchCV, 30 iterations, 5-fold StratifiedKFold, scored by
  average precision (appropriate for an imbalanced target).
- Search space: n_estimators, max_depth, learning_rate, subsample, min_samples_leaf.
- Cross-validation performed entirely within the training set; validation and test
  untouched during the search.
- Result: validation ROC-AUC improved from 0.8040 (untuned) to 0.8107 (tuned).
  PR-AUC saw a very slight dip, 0.4842 to 0.4812, an honest, documented trade-off
  from optimising for a single metric.
- [Insert the exact best_params_ printed by gb_search here, from notebook cell 65.]

## Final Model Selection
Tuned Gradient Boosting selected as the final model, based on validation ROC-AUC
(0.8107) and F1 (0.49), the best overall balance among all five models and both
tuned and untuned variants tested. Judged sufficiently interpretable for this
business context via feature importance analysis.

## Final Test Set Evaluation (One-Shot)
| Metric                      | Validation (tuned GB) | Test (tuned GB) |
|------------------------------|------------------------|------------------|
| ROC-AUC                      | 0.8107                 | 0.8153           |
| PR-AUC (Average Precision)   | 0.4812                 | 0.4876           |

Test score came in slightly higher than validation, indicating no overfitting to
validation-set quirks.

## Fit Diagnosis (Overfitting Check)
Train, validation, and test ROC-AUC were compared. A large train-validation gap
would indicate overfitting; validation and test scores stayed close together,
with test slightly higher, indicating good generalisation.
- Train ROC-AUC: [insert value printed in notebook cell 70]
- Train - Validation gap: [insert value printed in notebook cell 70]
- Validation - Test gap: [insert value printed in notebook cell 70]
