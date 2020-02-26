# Topic Modeling and Interpretation

## Creating the Topic Model
Using one question-response set as an example, we describe below the process for creating the topic model, building the topic browser, and interpreting the topic identities. 
A random sample of 849 University of Michigan undergraduate students responded to the question "What role did the arts play in your development as a person, friend, colleague, and student during college?" with an average response length of 17 words and standard deviation of 17 words.

Numbers, punctuation, and words from the SMART stop-word list were removed from the responses and all remaining words were stemmed. A custom stop word list containing ‘art’ and ‘arts’ was also used. All stems appearing in three or fewer responses were then removed and 37 responses containing no words were dropped (812 remaining responses in the dataset). The responses were then transformed into arrays of corpus dictionary indices, and a structural topic model {% cite roberts2014structural %} is created from them using the topic search technique from Lee and Mimno {% cite mimno2014low %}. The Lee and Minmo technique consistently overestimated the number of topics compared to what someone with knowledge of the domain area, the topic level of granularity, representativeness, and topic comprehensibility might select. 

17 cluster number estimations were run on the resulting topic prevalence matrix on a testing range of 7 to 30. Nine additional clustering estimators included in the package were ignored as they didn't produce meaningful results; always recommending the minimum number of clusters allowed. Held-out likelihood was near uniform for topic numbers above seven, with the highest index changing on each repeated computation and was therefore ignored. The three most frequent number of topics estimated were used as a starting point for manual inspection. 

Manual inspection included reading through several topic models with differing numbers of topics and/or stop-words. We prioritized human interpretation of the responses, how well the topics represented the domain, topic coherence (uniformity of the topics), and topic exclusivity (topic overlap and degree of difference from other topics).
 
Manual inspection and “tuning” was assisted with a custom-made interactive topic browser (Figure 1) which provided the ability to read associated keywords and representative documents in order to help interpret each child topic and parent nodes. The interactive visualization was created through hierarchical clustering of a dissimilarity matrix created from the topic prevalence matrix using the StmCorrViz R package {% cite stmCorrViz %}. 10 to 50 representative responses with a minimum topic proportion of 15% for the given topic were selected for each topic. Representative stems were found from combining metrics from the labelTopics function of the STM package in R were through weighted voting.
One topic was manually split into two because it picked up on the response structure of a complete sentence, but not the negation of the statement, so discrete negation and affirmation topics were created (“Played a Role” and “Didn’t Play a Role”).

## Topic Interpretation
Starting with the leaf nodes and working back towards the root of each topic tree, topic labeling and description of the model and clusters were completed by the research team. This team consisted of domain area experts with experience in the topic areas, and through close reading of representative stems, topic relationships, representative responses (10-50 per topic), and topic proportions, group discussion and interpretation led to further revision of the topic labels, along with topic descriptions and contextualization. The final topic model has 10 topics, and a 322 word dictionary.

We started with the question, “What role did the arts play in your development as a person, friend, colleague, and student during college?” From a sample of 812 student responses, we selected a topic model containing ten topics. With estimates of prevalence for each of the topics, we found the arts played a strong social role in creating (10%) and strengthening (8%) social bonds, supporting friendships (15%), and in their personal identity formation (9%). The arts also fostered different perspectives that helped them gain skills (12%), gain a deeper appreciation (11%), and become more open-minded through cultural understanding (12%) and finding a balance in life (14%). Another 7% indicated other miscellaneous roles, and only 2% of the responses indicated that the arts did not play a significant role. 

## Topic Results 
Tables 1-11 show the sets of topics identified from each question/response set, and they provide labels and prevalence estimates for each topic in the set. The average number of topics across of the questions analyzed was x. 


**Citations**
{% bibliography --cited %}