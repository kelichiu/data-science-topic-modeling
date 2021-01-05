# Data science topics from 1990s to 2020

## Summary

The result of the HDP Topic Modeling analysis informs us what data science scholars were talking over the course of 30 years. It is important because it helps us reflect on the evolution of data science and detect future direction of this field. We can see that in the 1990s, topics in data science were more about techniques and methods, but the domains of where they are applied were unclear. In the 2000s, the topics started to be more domain-specific and the range of domains was also broaden. In the 2010s, the domains expands even more, indicating that data science is applied to many more fields over the time. The year of 2020, which is the present year, the topics remain diverse and we see emergences of new topics. From the result, we infer that biology and health care will remain as the longstanding topics of data science, and there will be more topics of cloud computing in combination of city development, such as Smart Cities.

The topics are not always identifiable which draws the limitation of the method we employed. We conclude the three reasons for topics to be unidentifiable:

   * Words in the topics are non-English words
   * Words in the topics are too general to make the topic distinctive
   * The labeler's lack of domain knowledge

The labeling of the topics is a challenge in the field of Topic Modeling. In this project, we relied on human interpretation to label the topics. The subjectivity of human interpretation also brings bias in the the labeling. There are methods proposed to produce "objective" labeling of the topics. tomotopy Python package provides a function to label the topics automatically. The function is based on the paper Automatic labeling of multinomial topic models (2007), which proposes probabilistic approaches to automatically labeling topic models in an objective way. This approach marks the next step for us as the continuation of the research question.

## Data: Microsoft Academic Graph (MAG)
180,962 entries of data science paper abstracts were downloaded through Azure Databricks. The text data was preprocessed by removing digits, punctuations and stop-words. Lowercasing and stemming were also applied to the text tokens. The data is then divided into four subsets based on the year published in a 10 years interval. Abstracts from 1990 to 1999 are in one subset; 2000 to 2009, 2010 to 2014, and 2014 to 2019 are each in their own subsets. Finally, abstracts from the year 2020 are in its own subset. 

## Method: Topic Modelling
Topic modelling is a technique to extract hidden topics from a large size of corpus. There are many ways to conduct topic modeling analysis and one of them is Latent Dirichlet Allocation. LDA treats each document as the distributions of topics and each topic as the distributions of words. Therefore, a document has a mixture of topics instead of being categorized into a discrete group, which in a way reflects the typical use of natural language. Hierarchical Dirichlet Process (HDP) is an extension of LDA. While the underlying statistical principle is the same, the number of topics is given to a LDA model before training while a HDP model figures out the best number of topics during the training process. In our project, we employed HDP model from tomotopy Python package to conduct topic modeling analysis for the 30 years of data science paper abstracts. In addition, we will provide a deeper analysis to the topics generated in the year of 2020.
