# Board Game Analysis and Prediction

## PART 1
The 40 board games along with the board games that fans have liked (excluding the 40) are represented as nodes in the graph with edges corresponding to “fans liked”. In other words, two board games are linked if:
a. One of the board games is among the 40 board games, and
b. Fans that like one of the board games also like the other board game.
There are 320 nodes aka board games, and 975 edges or fans-liked relationships in the graph below.
![1](https://github.com/pooja-krishan/40-board-games/blob/main/1.png)

## PART 2
The node2vec method has been used to get the embeddings of the nodes and to draw them in 2D space. The first method in the Colab also helps to identify the vector of values that specify how similar a node is to the rest of the nodes. The first figure shows the visualization for the 40th board game in the graph. From the figures for both the graphs plotted to visualize the node embeddings of the first board game (not shown below), and the node embeddings of the 40th board game, it is clear that there are a lot of nodes that are not cluttered and are stand-alone signifying that they are not structurally similar to any other nodes. These correspond to the board games under the fans liked category which do not have a lot of connections to the other 40 board games, as seen in the graph from 1.
The second figure visualizes the node embeddings relative to all the nodes in the graph. Again, the stand-alone nodes correspond to games other than the top 40 board games.
![2](https://github.com/pooja-krishan/40-board-games/blob/main/2.png)
![3](https://github.com/pooja-krishan/40-board-games/blob/main/3.png)

## PART 3
The following figure below shows a bipartite graph where the board games are mapped onto various categories of the games. The next figure below shows a bipartite graph where the board games are mapped to the year in which they were released/created.
![4](https://github.com/pooja-krishan/40-board-games/blob/main/4.png)
![5](https://github.com/pooja-krishan/40-board-games/blob/main/5.png)

## PART 4
The first and second graphs below show that board games belonging to the same category or released in the same year respectively are connected.
![6](https://github.com/pooja-krishan/40-board-games/blob/main/6.png)
![7](https://github.com/pooja-krishan/40-board-games/blob/main/7.png)

## PART 5
### Problem: 
To build machine learning regression models to predict the average ratings of the 40 board games, and to select and report the metrics for the best-performing model.
### Solution: 
- The pandas data frame is modified by dropping the columns 'id', 'title', 'year', 'rank', 'rating', 'recommendations', 'types', and 'credit' and adding the columns ‘num of reviews’, and ‘avg rating’.
- The target Y label is the average rating column, and the X values correspond to the remaining features in the modified data frame.
- Principal Component Analysis does not give us great insights for feature selection, as seen from the graph in Colab, and so the best cut-off for features or the principal components is chosen by trial and error since the number of features is small.
- Linear Regression and k-nearest Neighbours are run in tandem and the best model selected for evaluation is Linear Regression with a negative RMSE of 0.164. The other metrics for Linear Regression on the test set are shown below.
![8](https://github.com/pooja-krishan/40-board-games/blob/main/8.PNG)

## Conclusion
This analysis provides insights into board game relationships, embeddings, and prediction models. It offers valuable information for understanding fans' preferences and predicting board game ratings.