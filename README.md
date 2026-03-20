## Project Description
RQ: “How does an online statement’s strength and direction of partisanship and accuracy effect its degree of social approval across communities?”

The goal of our project is to analyze how political partisanship language and the degree of factual information on a social media post affect its degree of social approval and engagement. We want to understand whether there is a relationship between a post containing language that leans more Democratic or more Republican and its social approval from the surrounding community. To test this, we will focus on discourse surrounding climate change and sustainability as they tend to be shaped by both factual, scientific neutral language as well as biased political language.

This question is important because online political discourse increasingly shapes how people understand public policy issues. Understanding what types of posts people are more likely to interact with, and the dynamics of social media platforms may have significant implications for policymakers and political actors as online communities represent a snapshot of voters' opinion on policy issues. Particularly as it concerns matters of climate change, which has a factual/scientific discourse that tends to be co-opted by political actors. It can help policy makers tweak their language when speaking about different topics across communities as well as revealing how politics shape discourse and opinions. We expect that higher accuracy and left-leaning partisanship will predict higher karma overall. We tentatively predict that there will be an inverse outcome if the post originates from a right-leaning subreddit. We predict this, as we feel the overall discourse on climate tends to be more salient in left-leaning circles, and so climate language may appear more often in Democratic Congressional speech, and may appreciate higher karma when accurate across contexts, whereas right-leaning communities may tend to give lower karma regardless of accuracy and punish left-leaning language.

## Additional Info:
- **Total lines of code**: 2,699 (approximate)

- **Methods and Analysis**: Our focus area is on the intersection of political science, linguistics/communication, and environmental policy. To study this relationship, we will combine three data sources: a dataset of Reddit posts about multiple climate-related topics, scraping pages of American congressional speeches that we will use to build a bag-of-words model to score the partisanship of natural language, and scraping and vectorizing Wikipedia articles relating to the same climate topics as the Reddit posts, operationalizing a post’s accuracy by its semantic similarity to the article vectors
  
- **Project strength**: Our project's strength is our combination of multiple datasets and variables in creating a coherent narrative and theory. While our visualizations and collection process support this ultimate goal, our regressions and the combination of our variables extracted from the respective datasets are innovative.

## Data

- [Climate_CSV and Climate_XLS](https://ieee-dataport.org/documents/social-media-big-dataset-research-analytics-prediction-and-understanding-global-climate): Downloaded
- [legislators_current.yml and legislators_historical.yml](https://github.com/unitedstates/congress-legislators?tab=readme-ov-file): Downloaded
- [*__articles.json](https://github.com/LibraryOfCongress/api.congress.gov): API
- [html_master.csv](https://api.govinfo.gov/docs/): API
- [wiki_texts](https://en.wikipedia.org/wiki/Main_Page): Scraped


## Libraries

**For Wiki_Dataset and analysis.ipynb**
- beautifulsoup4==4.14.3
- matplotlib==3.10.8
- nltk==3.9.2
- numpy==2.4.3
- pandas==3.0.1
- plotly==5.24.1
- PyYAML==6.0.1
- PyYAML==6.0.3
- Requests==2.32.5
- scikit_learn==1.8.0
- seaborn==0.13.2
- sentence_transformers==5.2.3
- statsmodels==0.14.2
- xlrd==2.0.2

**For Congress_Dataset**
- python=3.13.5
- pandas=2.3.3
- numpy=2.4.1
- ipykernel=7.1.0
- united-states-congress-python-api==0.0.2
- beautifulsoup4==4.14.3
- requests==2.32.5
- matplotlib==3.10.8
- seaborn==0.13.2

**For Climate_Dataset and Text_Embedding**
- python: 3.13.9
- pandas: 2.3.3
- numpy: 2.3.5
- matplotlib: 3.10.6
- seaborn: 0.13.2
- scikit-learn: 1.7.2
- xlrd: 2.0.2
- statsmodels: 0.14.5
- sentence-transformers: 5.2.2

## Contributions

- Emely Antunes Otsuka
    - All contents of Climate_Dataset and reddit_embedding.ipynb
- Jacob Rampino
    - All contents of Congress_Dataset; LMM and paths for analysis.ipynb
- Kayla Hammonds
    - All contents of Wiki_Dataset and Similarity_Analysis.ipynb; visualization and wrangling of analysis.ipynb
 
## AI Usage Statement

- congress_api.ipynb: AI was utilized to adapt Plot 1.1 from Plot 1 due to the long tail, to assist with debugging the mismatches with the Govinfo granules (specifically, what the fallback logic would consist of given what could be passed to the other endpoints), debugging checkpoint logic, and debugging by setting collapse_spaces: bool = False and adding csv.field_size_limit(sys.maxsize).
- partisan_score.ipynb: AI was used to expand the list of stopwords for the weighted word frequency model to ignore, and to assist with assigning the chamber variable for generating the speech by party bar chart due to issues with the variable name.
- analysis.ipynb: AI was used to assist in assigning variables and coloration to the 3D visualization.
- reddit_dataset_clean.ipynb: AI was used to identify the need to use the line of code ('openpyxl' if file.suffix == '.xlsx' else 'xlrd') that would properly load the two types of .xls files, to help debug implementation overlooks with the engagement rate formula that led to infinite values, and to identify methods to encode post tone variable from categorical to numerical (how we figured out to use the LabelEncoder package).

## Projects Links
- [Video](https://drive.google.com/file/d/19x1oZNDC2IRJFI9QI-2KEA7WHFoRKg1Z/view?usp=sharing)
- [Original Presentation](https://github.com/macs30112-winter26/final-project-climatebias/blob/main/Presentations/Climate_Bias_Presentation_original.pdf)
- [Updated Presentation](https://github.com/macs30112-winter26/final-project-climatebias/blob/main/Presentations/Climate_Bias_Presentation_Updated.pdf)
