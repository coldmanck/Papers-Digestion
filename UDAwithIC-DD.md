# Unsupervised Domain Adaptation with Imbalanced Cross-Domain Data
## Abstract
This paper address unsupervised domain adaption with imbalanced cross-domain data, especially in either (1) difference of label numbers across domains or (2) the data in the source and/or target domains might be collected from multiple datasets.

## Introduction
- Data collected by different users, using distinct sensors, at dissimilar scenarios, or during separate time periods are refered to in different *domains*.
- **Domain adaption** addresses the tasks in which training and test data are collected from source and target domains, respectively. They can be divided in two categories depending on the availibility of labeled data in the target domain during training: 
  - Semi-supervised domain adaption
  - Unsupervised domain adaption

### Semi-supervised domain adaption
**Either a small number of target-domain labeled data or cross-domain data pairs can be observed during training.** By utilizing the correspondence oinformation across scource and target domains, dictionary learning to derive a common feature space, which can be applied for the tasks of cross-domain classification and synthesis.

### Unsupervised domain adaption
**Only unlabeled data to be recognized can be observed in the target domain during training (no cross-doain instance pair is available)**. Therefore, how to transfer such information from the source domain becomes a challenging task. Based on *Maximum Mean Discrepancy* (MMD), recent approaches choose to eliminate the domain difference by matching cross-domain data distributions. The basic idea of such methods is to derive a common feature space, in which the marginal and/or conditional distributions of cross-domain can be matched.

