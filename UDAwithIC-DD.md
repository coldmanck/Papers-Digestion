# Unsupervised Domain Adaptation with Imbalanced Cross-Domain Data
T.-M. H. Hsu, C.-A. Hou, W.-Y. Chen, Y.-H. Tsai, Y.-R. Yeh, and Y.-C. F. Wang, "Unsupervised Domain Adaptation with Imbalanced Cross-Domain Data," *IEEE International Conference on Computer Vision* (ICCV), December 2015.
## Abstract
This paper address unsupervised domain adaptation with imbalanced cross-domain data, especially in either (1) difference of label numbers across domains or (2) the data in the source and/or target domains might be collected from multiple datasets.

## Introduction
- Data collected by different users, using distinct sensors, at dissimilar scenarios, or during separate time periods are refered to in different *domains*.
- **Domain adaptation** addresses the tasks in which training and test data are collected from source and target domains, respectively. They can be divided in two categories depending on the availibility of labeled data in the target domain during training: 
  - Semi-supervised domain adaptation
  - Unsupervised domain adaptation

### Semi-supervised domain adapattion
**Either a small number of target-domain labeled data or cross-domain data pairs can be observed during training.** By utilizing the correspondence oinformation across scource and target domains, dictionary learning to derive a common feature space, which can be applied for the tasks of cross-domain classification and synthesis.

### Unsupervised domain adaptation
**Only unlabeled data to be recognized can be observed in the target domain during training (no cross-doain instance pair is available)**. Therefore, how to transfer such information from the source domain becomes a challenging task. Based on *Maximum Mean Discrepancy* (MMD), recent approaches choose to eliminate the domain difference by matching cross-domain data distributions. The basic idea of such methods is to derive a common feature space, in which the marginal and/or conditional distributions of cross-domain can be matched.

However, existing approaches for unsupervised domain adaptation typically assume that 
- the label numbers of the source and target domains are the same, while the number of categories in the source domain is often larger than that in the target domain.
- the data of each class presented in the source or target domains exhibit similar data distributions (i.e. they come from the **same domain**), while both source and target-domain data may come from multiple datasets. 

This paper refer this as the presence of **imblanced cross-domain data**.  In this work, We propose an MMD-based algorithm of *Closest Common Space Learning* (CCSL). The major advantage of this CCSL is its ability in dealing with imbalanced cross-domain data for unsupervised domain adaptation. By exploiting label and structural information within and across domains, latent source domains can be identified for adaptation and recognition purposes.

Contributions of this paper:
- Propose *Closest Common Space Learning* (CCSL) to jointly solves instance reweighting and subspace which learns to learn the the latent sub-domains for adaptation.
- *Closest Common Space Learning* (CCSL) exploits both label and structural information for data within and across domains. This is achieved by relating latent source-target domain oaurs, with the ability to disregard irrelevant source domain instances during adaptation.
- In addition to achieving satisfactory performance on benchmark cross=domain classification datasets, our method perform favorably against recent unsupervised domain adaptation approaches on problems with imbalanced cross-domain data.
