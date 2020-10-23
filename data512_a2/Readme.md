
## Data-512: Assignment 2

# Bias in Data

### Contributors: 
[Aniruddha Dutta](https://github.com/aniruddha29)



### Description:
The purpose of this notebook is to explore and analyze the toxicity dataset from the Wikipedia Talk corpus, and indentify the source of inherent bias if present in the data.


### Data:
For the purpose of this assignment, we download the Wikipedia Talk labels dataset from [Figshare](https://figshare.com/projects/Wikipedia_Talk/16731). This data set includes over 100k labeled discussion comments from English Wikipedia. Each comment was labeled by multiple annotators via Crowdflower on whether it is a toxic or healthy contribution. We also include some demographic data for each crowd-worker.
We need the following data-sets for our analysis:

<b>Toxicity</b>
1. toxicity_annotated_comments.tsv
2. toxicity_annotations.tsv
3. toxicity_worker_demographic.tsv \
[available here-](https://figshare.com/articles/dataset/Wikipedia_Talk_Labels_Toxicity/4563973)

<b>Personal Attacks</b>
1. attack_annotated_comments.tsv
2. attack_annotations.tsv \
[available here-](https://figshare.com/articles/dataset/Wikipedia_Talk_Labels_Personal_Attacks/4054689) 

Documentation for the schema of the datasets are available [here](https://meta.wikimedia.org/wiki/Research:Detox/Data_Release#Personal_Attacks)

### EDA:
In this section we analyze the Toxicity dataset, to determine presence of any inherent bias in the data. 
The annotators from Crowdflower were responsible for labeling the comments as either 'toxic' or 'healthy'. They did this by giving each comment a toxicity score ranging from -2(very toxic) to +2(very healthy) with 0 being neutral. Then the comments which received a toxicity score < 0 were flagged as toxic(1). Hence it is logical to think that the labeling of the comments is impacted by the demographics of the Crowflower annotators.

In this section we will perform the following analyses:
- Analyze influence of worker demographic on toxicity annotations
- Identify most speech characteristics associated to toxicity
- Comparative analysis of speech characteristics between toxicity and personal-attacks



#### Analyze influence of worker demographic on toxicity annotations:

Gender difference plays a significant role in this scenario as people perceive and react differently to certain comments. Along with gender, age and education plays a very significant role in determining how a person will react to or interpret a comment/text. In this section we perform the following two analyses:
- Influence of gender and age
- Influence of gender and education
From our analyses, we found out that people in the age-groups of 18-45 have tagged most number of comments as 'toxic'. From an education perspective, doctorate students and professionals have fewer number of comments tagged. this can be associated to limited amount of leisure time that doctorate students and working professionals have, hence it can also be interpreted as them being more lenient with the annotations as they will try to finish through their quota of comments as soon as possible.

![Influence of gender and age on annotations.](https://github.com/Aniruddha2994/DATA-512/blob/main/data512_a2/eda_1.PNG)

![Influence of gender and education on annotations.](https://github.com/Aniruddha2994/DATA-512/blob/main/data512_a2/eda_2.PNG)

One interesting information that these graphs show that males have significantly more number of annoations than their female counterparts. But this doesnt mean that males tend to find comments toxic more often. But it is actually the opposite which is shown in the graph below:

![Influence of gender on annotations.](https://github.com/Aniruddha2994/DATA-512/blob/main/data512_a2/eda_3.PNG)

These plots prove that these is a bias present in the annotations data that originates from the worker demographics.


#### Identify most speech characteristics associated to toxicit
In this section we find the keywords most associated with toxic comments, to understand it's text characteristics.

To normalize the bias from worker demographic, we will subset the comments data for only those comments that are tagged as 'toxic' by more than 50% of the annotators. This will give us a relatively bias-free insight into the text characteristics.
  
Here we use the <b>nltk</b> package to tokenize and tag the comments inorder to identify and extract nouns, verbs and adjectives from the text present in the data.
We will then get the most frequent keywords associated with toxicity, using the 'Counter' function from the <b>collections</b> package.

From the analysis, we found the keywords most associated with 'toxicity' with 'fuck' and 'nigger' being present in 41.5% and 23.5% of the comments respectively. 

#### Comparative analysis of speech characteristics between toxicity and personal-attacks
Comments which are considered as toxic when directed towards to certain individual can be categorized as a personal attack. To establish this dynamic, we perform a comparison analysis between the text characteristics of comments labelled as 'personal attacks' and 'toxicity'.

![Comparison of keywords.](https://github.com/Aniruddha2994/DATA-512/blob/main/data512_a2/eda_4.PNG)


Future work:

From the previous analysis we can see that similar words (keywords) used in different context can label a comment as either toxic or a personal attack. In future work, I would like to explore key_phrases instead of words to try an capture the sentiment and context of the comment and then compare beteen the two datasets.

### Licenses:

This assignment is licensed under the terms of the [MIT license](https://github.com/Aniruddha2994/DATA-512/blob/main/LICENSE.md)

