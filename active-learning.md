/ [Home](index.md)

# Active Learning

Active learning is a semi-supervised machine learning algorithm in which the algorithm can interactively query a user or some other information source to label the unlabelled data. It is used in situations where there is a large amount of unlabelled data and manual labelling is expensive.

In active learning, the algorithm will choose a subset of examples to be labelled from the available unlabeled data. Since the algorithm chooses the examples it wants to learn from, the data required to learn a concept is much lower than supervised learning.

The three type of active learning are:

- Stream-based selective learning - Each unlabelled data is examined one at a time and the algorithm decides whether to label the data or immediately query the user.

- Pool-based learning - The entire dataset is examined first and the algorithm selects the best query or set of queries.

- Membership query synthesis - algorithm generates its own instance of data from the data provided which is then queried. Useful if dataset is small.

<br>

**Created by Santhosh Kannan**

---

<br>
