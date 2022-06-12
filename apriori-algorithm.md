/ [Home](index.md)

# Apriori-algorithm

All non-empty subset of frequent itemset must be frequent. The key concept of Apriori algorithm is its anti-monotonicity of support measure. Apriori assumes that

All subsets of a frequent itemset must be frequent(Apriori property).
If an itemset is infrequent, all its supersets will be infrequent.

The algorithm examines three crucial aspects while constructing association rules between components or items: support, confidence, and lift

-Association rule: For example, X Y is a depiction of discovering Y on a basket that contains X.
-Itemset: For example, X,Y is a representation of the list of all objects that comprise the association rule.
-Support: Transactions containing the itemset as a percentage of total transactions
-Confidence: Given X, what is the likelihood of Y occurring?
-Lift: Confidence ratio to baseline likelihood of occurrence of Y

<br>

**Created by kishore**

---

<br>