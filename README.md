# Predicting Appeal: M.Sc. Thesis Project

This repository contains the code, data, and documentation for my M.Sc. thesis titled "**Predicting Number of Property Assessment Appeal Received by Property Assessment Organizations using Neural Network**" at **University of British Columbia**. The project focuses on predicting appeal using machine learning techniques.

## 📜 Abstract

*The annual fluctuation in property assessment appeals submitted to property assessment organizations presents a significant resource planning challenge. Inaccurate forecasting of appeal volumes leads to operational inefficiencies, delays in processing, 
and suboptimal resource allocation. This M.Sc. thesis research directly addresses this problem by proposing the development and evaluation of a predictive model based on Neural Networks (NNs). The primary objective is to leverage the ability of NNs to 
capture the complex, non-linear relationships driving appeal volumes. The model will be trained using historical data from a property assessment organization in Canada from 2019 - 2025. Since the data are highly imbalanced - number of properties with appeal are very smaller than those without appeal - NN model’s prediction is evaluated using Precision (PPV - Positive Predictive Value) and Recall (Sensitivity). Furthermore, recognizing the ”black box” nature of NNs, this project will employ SHAP (SHapley Additive exPlanations), to interpret the model’s predictions. This will provide factors influencing appeal predictions and how the model arrives at its conclusions. The expected outcomes include a validated NN model that can serve as a practical tool to help property assessment corporation’s resource planning, along with a data-driven understanding of the key drivers influencing property assessment appeals in British Columbia.*


## 🎯 Project Goals

* **To develop, evaluate, and interpret a Neural Network (NN) model capable of predicting the likelihood of property assessment appeals for assessment organizations.**
---

## Dataset

The dataset used in this project is sourced from a organization responsible for property assessment in a provice in Canada. In line with the organization’s data security policies, all records have been anonymized before being shared for analysis. Two comprehensive datasets are expected, capturing historical appeal activity related to property assessments from 2019 through 2024. This organization operates a two-stage appeal process within each tax year. The first appeal window opens on early in the calendar year, shortly after property owners receive their annual assessment notices. During this phase, property owners or their representatives can submit an appeal if they believe the assessed value is inaccurate. These appeals are then reviewed by a panel over the following weeks. Most cases are resolved during this initial cycle. However, if additional time is required or if the property owner disagrees with the panel’s decision, the appeal is escalated to the second cycle, which accepts further appeals for the same properties up to early summer. The datasets include a wide range of attributes to support analysis. These include a unique property identifier, tax year, geographic region and jurisdiction, property classification (e.g., residential or commercial), dwelling type (e.g., apartment, house, duplex), and land quality indicators (such as value per unit area). Additional fields capture the method of submission (email or mail), assessed values for land, building, and total property, and whether the structure is completed or under construction. The data also contains the values proposed by the appellants, the valuation methods used (typically one of two modeling approaches), appeal status, final decision outcomes, panel notes, and—if applicable—the rationale for progressing to the second appeal cycle. Although the dataset is generally of high quality and already well-cleaned, further data transformation and preprocessing will be necessary to prepare it for modeling. The following table summarizes the number and percentage of properties appealed each year since 2019:

---

## 🛠️ Methodology

Framing this problem as a classification task is appropriate. This approach involves evaluating each property
individually to predict its likelihood of appeal. Special considerations are necessary to address the resulting class imbalance in the dataset. Common techniques
to mitigate this issue include downsampling (training on a reduced subset of the
majority class, i.e. non-appealed properties) and upweighting (assigning higher
weights to the minority class during training). Among the classification methods discussed, Neural Network are proposed as the preferred approach. While
logistic regression is simple to fit and interpret, it cannot capture nonlinear relationships or complex interactions between features. Similarly, Support Vector
Machines, like other kernel-based methods, struggle with large datasets. Neural
Networks excel with large-scale data, detecting complex patterns and feature
interactions effectively. NNs allow us to use an extensive dataset to incorporate
all potential co-variates while identifying the most influential ones. Additionally,
SHAP can be applied post-training to interpret the NN’s predictions, ensuring
transparency despite the model’s complexity.


---

## 📂 Repository Structure
* **`/Training & Test/`**: This directory contains materials related to the training and testing phases of our models or analyses.
    * **`/Training & Test/Unbalanced Dataset/`**: This sub-directory focuses specifically on datasets and methodologies concerning imbalanced data.
        * **`Unbalanced-Dataset.html`**: An HTML report detailing the experimental setup and results for the unbalanced dataset scenario.
          * You can view this report directly in your browser: [View the Unbalanced Dataset Report](https://hamedheli.github.io/Appeal-Prediction/Training%20%26%20Test/Unbalanced%20Dataset/Unbalanced-Dataset.html)
