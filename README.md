# Board Game Analysis and Prediction

## Part 1
The graph consists of 320 nodes representing board games. These include the 40 main board games and additional board games liked by fans. Nodes are connected by edges indicating the "fans liked" relationship. In this context, two board games are linked if:
- One of the board games is among the 40 main board games.
- Fans who like one board game also like the other board game.
There are a total of 975 edges representing these relationships.
![1](https://github.com/pooja-krishan/40-board-games/blob/main/1.png)

## Part 2
Node2Vec, a technique for obtaining node embeddings, is used to visualize the nodes in 2D space. The first method identifies the similarity vector of a node to the rest of the nodes. The first figure visualizes the embeddings of the 40th board game. Comparing this visualization with that of the first board game reveals that there are stand-alone nodes, indicating board games with fewer connections to the top 40 games. These likely correspond to the less-connected board games in the "fans liked" category.
![2](https://github.com/pooja-krishan/40-board-games/blob/main/2.png)
![3](https://github.com/pooja-krishan/40-board-games/blob/main/3.png)

## Part 3
A bipartite graph showcases the mapping of board games to different game categories. Another bipartite graph displays the mapping of board games to their respective release years.
![4](https://github.com/pooja-krishan/40-board-games/blob/main/4.png)
![5](https://github.com/pooja-krishan/40-board-games/blob/main/5.png)

## Part 4
The first and second graphs illustrate connections between board games in the same category and those released in the same year, respectively.
![6](https://github.com/pooja-krishan/40-board-games/blob/main/6.png)
![7](https://github.com/pooja-krishan/40-board-games/blob/main/7.png)

## Part 5
### Problem:
To build machine learning regression models predicting the average ratings of the 40 main board games and report metrics for the best-performing model.
### Solution:
- Data preprocessing involves modifying the pandas data frame, dropping and adding relevant columns.
- The target label (Y) is the average rating column, and the remaining columns are used as features (X).
- Principal Component Analysis (PCA) analysis is performed, although it doesn't provide significant insights for feature selection.
- Feature selection cutoff or principal components are chosen through trial and error.
- Linear Regression and k-nearest Neighbours models are evaluated, with Linear Regression performing the best (negative RMSE of 0.164).
- Metrics for Linear Regression on the test set are reported.
![8](https://github.com/pooja-krishan/40-board-games/blob/main/8.png)

## Conclusion
This analysis provides insights into board game relationships, embeddings, and prediction models. It offers valuable information for understanding fans' preferences and predicting board game ratings.