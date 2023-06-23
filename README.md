# Automated Identification of Healthier Food Substitutions through a combination of Graph Neural Networks and Nutri-Scores

The increased incidence of chronic diseases globally has made the healthy diet increasingly important, as it is one of the factors that can support maintaining health and prevent the chronic diseases. Unhealthy diets are known to be associated with an increased risk of a variety of health issues and diseases. However, individuals often struggle to make healthy dietary choices due to various factors including personal preferences and taste. To address this issue, we have developed an approach that can recommend healthier alternative food products in individuals' current diet to encourage them to introduce changes in their diets. To this end, our proposed recommendation algorithm consists of two parts. The first part automatically generates food substitutions using Graph Neural Networks; the second part identifies healthier food recommendations employing the Nutri-Score algorithm and ranks these healthier food options according to their highest Nutri-Score. We applied the classical and most common variants of Graph Neural Networks (GNNs), which are GraphSAGE and Graph Attention Network (GAT), to automatically generate food substitutions. Our best results were achieved with GAT and by putting the recommended substitutes in the same food category as the query food. The specific results achieved were a Recall Rate of $0.647$ and $0.733$ for the top $5$ and $10$ results, respectively, which is a good performance for a recommender system. By secondly employing the French nutritional rating system Nutri-Score to identify healthier food recommendations, we found that simply ranking our food recommendations by the highest Nutri-Score is sufficient to claim that the final substitutions have are more nutritious than the food in question.

### Setup

The Knowledge Graph of Food can be downloaded [here](https://drive.google.com/drive/folders/1p3L-lBbx_2cBbjTBXimfR3DntmZ8AEpS?usp=share_link) and should be added to ```Input Data```.

### Quick Tour

- ```Notebook/1_Prep_Data.ipynb```: takes as input the Knowledge Graph of Food and outputs Node and Edge dataframes.
- ```Notebook/2_Model.ipynb```: takes as input the Node and Edge dataframes, applies Graph Neural Networks and outputs new node representations/Food Embeddings.
- ```Notebook/3_Evaluate_Model.ipynb```: takes as input the Food Embeddings and evaluates the models by computing Mean Average Precision, Mean Reciprocal Rank and Recall Rate at 5 and 10.
- ```Notebook/4_Pred_New_Links.ipynb```: takes as input the Food Embeddings and predicts new "isSubstitutedBy"-links between food-food pairs.
