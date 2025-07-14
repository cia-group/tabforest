
# Code the Change: NLP Models for Agroforestry Paper Relevance Prediction

[(click here for a video walkthrough of this repository)](https://youtu.be/83Tp07NF_UI)

We worked with [Susan Cook-Patton, Ph.D.](https://www.linkedin.com/in/susan-cook-patton-ph-d-3904a448/) and the Tackle Climate Change (TCC) team from [The Nature Conservancy](https://www.nature.org/en-us/) to streamline their agroforestry evidence synthesis process. 

We built language models that can read the title and abstract of a paper and predict whether it is relevant for the TCC team. See linked slide decks of our [interim](https://github.com/cia-group/tabforest/blob/main/presentation_slides/TAB%20Interim%20Pres.pdf) and [final](https://github.com/cia-group/tabforest/blob/main/presentation_slides/TAB%20Final%20Pres.pdf) presentations of our work. 

Our final product is a [Google Colab](https://github.com/cia-group/tabforest/blob/main/run_models.ipynb) where the TCC team can run these models themselves and get relevance predictions for new collections of agroforestry publications. 

## Use Instructions:

Prior to using this colab, you must obtain a table of preliminary papers with title and abstract information, such as by conducting a basic search on Web of Science. Once completed, follow the steps below to get predictions for which papers are relevant. 

1. Go to the [run_models.ipynb](https://github.com/cia-group/tabforest/blob/main/run_models.ipynb) google colab and click the “Open in Colab” blue button at the top to open a copy of the notebook. 
2. Follow the instructions in the Colab notebook, or follow along with this [video walkthrough](https://youtu.be/SKrD9qxU9mw).
3. After your predictions are completed, you can read through the papers that were predicted as relevant and conduct your research from there. 
4. See the sections below for more information on the available models, precision and recall, and troubleshooting advice. If you have any questions, please feel free to contact us! 

Note: This tool is intended to be used in the TCC team’s agroforestry evidence synthesis pipeline. As such, it was trained on papers about agroforestry with specific criteria for relevance (see Training Notes). The models may not perform as reported if you input papers unrelated to agroforestry or have different criteria for relevance. 

## Contributors

**Charlotte Chang (Principal Investigator):** \
&emsp;Assistant Professor of Biology and Environmental Analysis at Pomona College 

All students trained a variety of different language models and co-coded to run their respective best performing models in the run_models.ipynb final product. 

**Laura Vairus (Student Lead):** \
&emsp; Student at Harvey Mudd College \
&emsp; SciBERT, MiniBERT, and Naive Bayes model \
&emsp; contact: lvairus@hmc.edu | [linkedin](https://www.linkedin.com/in/lauravairus/)

**Alyssa Wu:** \
&emsp; Student at Pomona College \
&emsp; SPECTER models \
&emsp; contact: zjwualyssa@gmail.com | [linkedin](https://www.linkedin.com/in/zjwualyssa/)

**Wendi Zheng:** \
&emsp; Student at Columbia Univeristy \
&emsp; BERT Precision models \
&emsp; contact: wendizheng06@gmail.com | [linkedin](https://www.linkedin.com/in/wendi-zheng-442588235/)

## Best Performing Models

| Model Name    | Precision | Recall | Notes  |
| :-------------: | :---------: | :------: | :------ |
| BERT            |  0.70     |  0.27  |  **highest precision** (read through least amount of irrelevant papers but capture less relevant papers from input)      |
| MINIBERT        |  0.53     |  0.54  | of the bert models, the smallest and quickest to run      |
| SCIBERT         |  0.52     |  0.55  |  largest model (takes most time/compute power to run)      |
| SPECTER-1LAYER  |  0.33     |  0.77  |  of the specter models, the smallest and quickest to run      |
| SPECTER-3LAYER  |  0.22     |  0.96  |  **highest recall** (capture more relevant papers from input but sort through more irrelevant papers)      |
| NAIVEBAYES      |  0.33     |  0.81  |  smallest model (takes least time/compute power to run)      |

## Precision and Recall

- Precision: what percentage of the predicted relevant papers are truly relevant
- Recall: what percentage of all truly relevant papers get predicted as relevant
- Maximize precision if you want to sift through the least amount of irrelevant papers, but keep in mind you will miss a larger fraction of truly relevant papers, since they will be mistakenly classified as irrelevant.
- Maximize recall if you want to capture the most relevant papers from your given set, but keep in mind you will have to sift through more irrelevant papers that were mistakenly classified as relevant

## Colab Troubleshooting

- If you get an error, first try looking for our manually printed error, which should explain more clearly what went wrong and how to fix it. It will be right below the cell you just ran and will start with “ERROR”, before any of the red colored text.
- If you get an unknown error, try reloading the page and starting from scratch by rerunning the top code cell again (which installs the required libraries to set up the environment).
- If you get any warnings, you should be able to ignore them.
- If you have any questions, please feel free to contact us!

## Training Notes

- Our training data consisted of agroforestry papers from Web of Science (WoS) searches that were manually classified as relevant or irrelevant by the TCC team over previous years.
- TCC criteria for relevance: Publications must provide
    1. A description of the agroforestry system (system type, management practices, location, etc.) 
    2. Field derived biomass or carbon estimates in t/ha for aboveground, belowground, or soil pools
    3. A non-agroforestry reference in the case of soil pool carbon estimates
- training data files information:
    - TAB_binaryLabel.csv: Manually labeled publications from a WoS search in August 2021
    - TAB_binaryLabel_all1sTrue.csv: classified non-agroforestry papers that were relevant in other projects as relevant to counter the class imbalance
    - TAB_new.csv: Additional publications from a WoS search in September 2022 to the TAB_binaryLabel.csv
