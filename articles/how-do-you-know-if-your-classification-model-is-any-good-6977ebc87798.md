/ [Home](../index.md) / [ML Archve](index.md)

# How Do You Know if Your Classification Model Is Any Good?

**Note:** Guidance for determining whether your model is successful in the context of your goals

If you are new to machine learning and you developed a classification model, then congrats! You might be thinking, “now what?”

That’s a great question.

With auto ML technology, model creation is more accessible than ever. The difficulty lies in determining if that model is any good. In this article, I will explore how to determine if your model is satisfactory for your business use case (spoiler: it’s not black and white).

#### What Kind of Classification Are We Talking About?
Before I jump into how to evaluate your classification model, I want to clarify that while the examples I give in this article are all binary classification, there are also multi-class classification problems. The difference is that in binary classification, the target variable has only two values, and in multi-class, it has more than two values.

Many of the metric calculations I talk about later in the article will change slightly for a multi-class model, so make sure to look up the correct formula if that is the kind of model you are evaluating.

#### Comparing Your Model to the Baseline

**Machine learning model performance is relative and ideas of what score a good model can achieve only make sense and can only be interpreted in the context of the skill scores of other models also trained on the same data.” -Jason Brownlee, machinelearningmastery.com**

Since every machine learning dataset is different, success is subjective.

The only way to make evaluating machine learning models truly objective is to compare different models on the same dataset. And, like a science experiment, we need a “control group.” A control group in an experiment would be where there was no intervention, and results were measured. This is where the baseline model comes in.



You can think of a baseline model as little to no intervention. In a classification model, this would be where you just guess whichever result occurs most (i.e., the mode) — for every observation. So… not much of a model. But it is a helpful baseline so that when you evaluate your model, let’s say it’s detecting fraud, you can say, “hey, my logistic regression model performed 40% better than if I randomly assigned transactions as fraudulent or not!” (This random assignment is the “no skill” line on the ROC curve, which I will cover in more detail later.)

Another way to establish your baseline is to look at what your business is currently doing without machine learning. Whether it’s manually checking certain criteria, using formulas (like if/then statements), or something else — compare the success rate of that process to your model.

#### Identifying Measures of Success
Once you have a baseline model and other model options to compare it to, we can start to talk about success metrics. How will you score your model against the baseline? Before we review the performance metrics options, there are a few considerations to have in mind.

#### Identifying Risk Tolerance
How comfortable are you with your model making a mistake? What would the real-world consequences be?

These are good questions to ask when thinking about how risk tolerant your use case is. And your answers can guide you on which metrics to use to evaluate the model and what thresholds to set for them.

For example, if your model is predicting whether someone has a disease or not, you are very risk averse. The consequences associated with a false negative — telling someone that they don’t have a disease when they actually do — are high.

When we talk about false negatives, true positives, and so on, it can get confusing. (The matrix of these values is even called a confusion matrix — talk about self-awareness.) So here’s a quick reference visual before we jump into calculating performance metrics, using the same example as the last paragraph:

#### Class Imbalance
Another thing to identify before selecting metrics to evaluate your model is class imbalance. A dataset with balanced classes would contain around the same number of observations for both positive and negative instances of the target variable.

Depending on your use case, it might not be feasible to have balanced classes. For example, if you want your model to detect spam emails, then a positive value of the target variable would mean that the email is spam. The majority of emails sent are not spam, however, so your dataset is bound to be naturally imbalanced. No need to panic! Just keep this in mind when you select a metric to evaluate your model — choose one that is less sensitive to class imbalance.

#### Performance Metrics for Classification
Below are some metrics used to evaluate a classification model. This is not a comprehensive list, but it does cover the most common metrics:

Accuracy: the accuracy of a model is the ratio of correct predictions to the total number of predictions.

* When to use it: When your classes are balanced, and you want to predict both classes correctly. There are drawbacks to using accuracy alone if your classes are imbalanced — if there are few observations for your minority class, then even if the model got all of those wrong, it could still have a high accuracy score.

* Example: If you have a model that predicts whether an image contains a cat or a dog, you are interested in the correct predictions for both classes, and one type of misclassification does not present more risk than another. Accuracy would be a good way to evaluate this model.


Precision: the precision of a model is the ratio of true positives to the sum of true positives and false positives. In plain English, this is the proportion of positive identifications of the target variable that were correct.

* When to use it: When you want to minimize false positives.
* Example: For the spam email prediction model, a false positive would have bad consequences for the email recipient — the model would identify a regular email as spam (false positive), and it would be sent to another folder when really that email contained valuable information. In this case, you would want to use precision to evaluate the model.

Recall: the recall of a model (sometimes referred to as sensitivity) is the ratio of true positives to the sum of true positives and false negatives.

* When to use it: When you want to minimize false negatives.
* Example: For the disease prediction model, you really don’t want to tell someone they do not have a disease when they do (false negative), so you would want to use recall to evaluate your model.

Area Under Curve (AUC): this metric measures the area underneath the ROC curve, which is a plot of true positives and false positives at different classification thresholds.

* When to use it: When you want to make sure that your model outperforms the no-skill model or you want to look at the overall performance of the model.
* Example: The image below shows an AUC curve for a poor-performing model. The dotted line depicts the random guesses (the no-skill model) — so for this model, with an AUC of .54, it is just barely performing better than guessing.


F1 Score: the F1 score measures a model’s performance on the positive class. It is the harmonic mean of precision and recall.

* When to use it: When you are interested in both precision and recall. It also works well on imbalanced datasets.

* Example: For the disease prediction model, you may decide that both telling someone they don’t have a disease when they are sick and telling them they do have it when they are fine are bad outcomes. Since you want to minimize both of those occurrences, the F1 score is a good choice to evaluate your model.

#### Overfitting and Underfitting
After you have determined that your model performs well against the baseline model, you still aren’t finished! Now you need to evaluate the results with a test dataset. This is often done by holding out a percentage of your dataset from training so that you can use it to test your model. A more advanced method for testing is cross-valiation — this technique uses multiple iterations of training and testing with data subsets and reduces some variability that occurs when testing only occurs once.

If your model performs very well on the training dataset and not very well on the test dataset, then you have a case of overfitting — your model fits the training data so well that it cannot fit other datasets. Having a train, test, and validate split is considered best practice and helps prevent overfitting. To read more about the difference between test and validation datasets, check out this article.

If your model does not perform well on the training or test dataset, then you may have a case of underfitting. It is a good idea to look at other model options before discarding the use case.

#### Conclusion
It is my hope that now you have an idea of whether your machine learning model is a good one. If you’ve realized that your model isn’t up to snuff, look out for my next article, where I go over what to do if your model isn’t performing.


https://towardsdatascience.com/how-do-you-know-if-your-classification-model-is-any-good-6977ebc87798