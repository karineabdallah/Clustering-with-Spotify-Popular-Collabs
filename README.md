# Graphs and clustering with R to study collaborations between artists

Karine ABDALLAH

The goal of this project is to study some social graphs and to analyze the links between the individuals that constitute the network. I chose to focus on the most listened musical collaborations from 2000 to 2020 on Spotify. 

After processing the data with Python (see IPYNB file), the databases at our disposal are :

- nodes representing the artists: name, genre, sub-genre, list of artists with whom the artist has collaborated, degree representing the number of collaborations with different artists

- the edges representing the undirected links between artists: artist A, artist B, list and number of songs in common.
We also have metadata about the artists: name, popularity, median year of the songs in which they collaborate, and musical characteristics.

We first studied the collaborations by musical genre. Then, we analyzed centrality measures to identify important nodes. We finished on community detection using clustering algorithms.

##1.	Collaborations by genre

The pop genre is quite diverse, but most of the well-known pop artists are actually "dance pop" artists, which is also known to be commercial.  
The two most represented hip hop sub-genres are the historically known Atlanta hip hop and the later alternative hip hop.
The vast majority of known Latin American artists are reggaeton artists.
Within a genre, the network is built around one or two sub-genres that dominate the market.

##2.	Collaborations of connected artists

We have selected the artists who have a degree higher or equal to 15 to study more finely the collaborations. We notice 2 groups: 1 Latin group and 1 hip hop/pop group. The Latin and hip hop artists collaborate little. Indeed, the Spanish-speaking artists have an interest in collaborating with pop artists to seduce a mass audience.

##3.	Centrality measures

We have identified the 10 artists who stand out, according to different measures of centrality:
- Centrality of degree : influential artists in their respective genres
- Centrality of proximity : pop artists, at the heart of the network of collaborations
- Centrality of intermediality : artists frequently linked to other genres.

##4.	Communities detection and analysis

The idea is to apply clustering algorithms on our data and to identify the criteria for creating clusters. Our graph contains 89 nodes connected by 519 edges.

The spectral clustering gave three groups: 2000s artists, reggaeton artists and hip hop artists.

The Girvan-Newman algorithm produces two unequal groups that differ in their proximity centrality.

The Clauset-Newman method yields three groups: a reduced group with little information, and two other groups that are distinguished by their proximity centrality.

The Louvain algorithm also displays three unbalanced groups. The information we have does not allow us to identify the corresponding communities.

Nevertheless, the three previous algorithms show similar results.

The random walk method, based on Markov chains, identifies four groups. The 4th group is characterized by low degrees, thus corresponding to the least influential artists. Group 3 includes a majority of hip hop artists with low proximity centrality. On the other hand, the genres are equally distributed in groups 1 and 2. 

The optimal method, on artists with degree greater than or equal to 25, gives four balanced groups. The artists in group 3 are concentrated in the period 2015-2017 and have low proximity centrality. Cluster 4 has specific musical characteristics, such as relatively low instrumentality and acousticity. One may want to dig into the track of communities based on the artistic universe. 

We evaluated the clustering algorithms with the modularity measure. The higher the modularity measure, the more internally connected and separated the clusters are, thus the more efficient the algorithm is. The spectral clustering algorithm has the best modularity, followed by the Louvain algorithm. 

A Principal Component Analysis was used to identify musical characteristics by genre. Hip hop is characterized by a very marked tempo and an important speechiness. Reggaeton, on the other hand, is danceable, energetic and positive. Pop music has reinvented itself to remain the popular genre par excellence.
