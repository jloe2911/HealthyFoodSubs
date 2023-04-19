# Automated Identification of Healthy Food Substitutions based on Similarities in Nutritional Value and Flavor

As the incidence of chronic diseases increases, and with an unhealthy diet being one of the leading health risks globally, a healthy diet has become more and more important. An unhealthy diet is associated with an increased risk of a variety of health issues and diseases. However, even though healthy, nutritious diets are known to be important and are one of the most basic human needs, it is very common that individuals do not always make healthy dietary choices. A potential solution to this problem is to help people change their diet by developing a system that can recommend “healthy” alternative ingredients to ingredients in an individual's current diet. Consequently, in this work, we apply the classical and most common variants of GNNs, which are GraphSAGE and Graph Attention Network (GAT), to automatically generate food substitutions. We obtained the best results with GAT by restricting the recommended substitutes to be in the same food category than the query food. Specifically, we achieved a Recall Rate of $0.647$ and $0.733$ for the top $5$ and $10$ results, respectively, showing significant performance for a recommender system. We further employed the French nutritional rating system Nutri-Scores to identify “healthier” food recommendations. Hence, our final recommendation algorithm consists of two parts. The first part automatically generates food substitutions using Graph Neural Networks. While the second part identifies “healthy” food recommendations employing the Nutri-Scores' algorithm and ranks these “healthy” food options according to their highest Nutri-Score.

### Setup

The Knowledge Graph of Food can be downloaded [here](https://drive.google.com/drive/folders/1p3L-lBbx_2cBbjTBXimfR3DntmZ8AEpS?usp=share_link) and should be added to ```Input Data```

### Quick Tour

- ```Notebook/1_Prep_Data.ipynb```: takes as input the Knowledge Graph of Food and outputs Node and Edge dataframes.
- ```Notebook/2_Model.ipynb```: takes as input the Node and Edge dataframes, applies Graph Neural Networks and outputs new node representations/Food Embeddings.
- ```Notebook/3_Evaluate_Model.ipynb```: takes as input the Food Embeddings and evaluates the models by computing Mean Average Precision, Mean Reciprocal Rank and Recall Rate at 5 and 10.
- ```Notebook/4_Pred_New_Links.ipynb```: takes as input the Food Embeddings and predicts new "isSubstitutedBy"-links between food-food pairs.
