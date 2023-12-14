# Training an explainable multivariate machine learning model

## Business Objectives
The goal of the project is to use machine learning to also understand how distributor/customer behavior metrics drove revenue in a flexible way. Explanations can be taken upstream to c-suite to understand customer behavior for the whole business, and it can be taken downstream to account managers for tacticle interventions for their specific set of accounts. While this method was used in a real business context, here I used a dummy dataset of distributor information for a business.

## Technical Overview
This project uses XGboost to train a multivariate model to make predictions about revenue, based on distibutors and customer behavior metrics. Cross-validation using CV grid search was used to tune the model, and explainability of the model was generated using SHAP values to understand feature importance, both at a local and global level (i.e individual distributor, and across all distributors). 

## Output of Project
### Impact on whole business (Global explanations)
XGBoost + SHAP allows for analysis of distributor metric impact on revenue for the whole business.
![global_shap](https://github.com/dkwik/business-revenue-analysis/assets/89932747/0aa53d08-0f6d-4fda-ad3d-f9c730427309)

### Impact on individual distributor (Local explanations)
But also allows for explanations for individual distributors.
![waterfall_shap](https://github.com/dkwik/business-revenue-analysis/assets/89932747/2785abd9-9cee-43b2-a2e2-b06fd7e92334)

### Creation of interactive yearly explanations
Limitation of SHAP package is that waterfall charts analyze a distirbutor vs average over all distributors. Here we devise a way to analyze shap impact between a distributor and their own performance last year.
![waterfall](https://github.com/dkwik/business-revenue-analysis/assets/89932747/3aed9a59-2998-41b3-83b9-e46bf40ffee6)
