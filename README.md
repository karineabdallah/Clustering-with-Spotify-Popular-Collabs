# Spotify_most_listened_collabs

Magistère 3 - Projet théorie des réseaux et modélisation
Les collaborations musicales 2000-2020 les plus écoutées sur Spotify
Karine ABDALLAH
L'objectif de ce projet est d'étudier un graphe social et d'analyser les liens entre les individus qui constituent le réseau. J'ai choisi de m'intéresser aux collaborations musicales des années 2000 à 2020 les plus écoutées sur Spotify. 
Les bases de données à notre disposition sont :
•	les noeuds représentant les artistes : nom, genre, sous-genre, liste d'artistes avec lesquels l'artiste a collaboré, degré représentant le nombre de collaborations avec des artistes différents
•	les arêtes représentant les liens non orientés entre artistes : artiste A, artiste B, liste et nombre de chansons en commun.
Nous disposons également de métadonnées sur les artistes : nom, popularité, année médiane des chansons où il collabore, et caractéristiques musicales.
Nous avons d’abord étudié les collaborations par genre musical. Ensuite, on a analysé les mesures de centralité pour identifier des noeuds importants. On a terminé sur la détection de communautés à l’aide d’algorithmes de clustering.

1.	Collaborations par genre

Le genre pop est assez hétéroclite mais la plupart des artistes pop connus sont en réalité des artistes de "dance pop", qui est d'ailleurs réputée commerciale.  
Les deux sous-genres hip hop les plus représentés sont le hip hop d’Atlanta, historiquement connu, et le hip hop alternatif, arrivé plus tard sur le marché.
L'immense majorité des artistes latino-américains connus sont des artistes de reggaeton.
Au sein d'un même genre, le réseau est construit autour d'un ou deux sous-genres qui dominent le marché.

2.	Collaborations des artistes connectés

On a sélectionné les artistes qui ont un degré supérieur ou égal à 15 pour étudier plus finement les collaborations. On remarque 2 groupes : 1 groupe latin et 1 groupe hip hop/pop. Les artistes latino et hip hop collaborent peu. En effet, les artistes hispanophones ont intérêt à collaborer avec des artistes pop pour séduire un public de masse.

3.	Mesures de centralité

Nous avons identifié les 10 artistes qui se distinguent, selon différentes mesures de centralité :
-	Centralité de degré : artistes influents dans leurs genres respectifs
-	Centralité de proximité : artistes pop, au cœur du réseau de collaborations
-	Centralité d’intermédiarité : artistes fréquemment liés aux autres genres.

4.	Détection et analyse de communautés

L’idée est d'appliquer des algorithmes de clustering sur nos données et d'identifier les critères de création des groupes. Notre graphe contient 89 noeuds reliés par 519 arêtes.
Le clustering spectral a donné trois groupes : les artistes des années 2000, les artistes reggaeton et les artistes hip hop.
L'algorithme de Girvan-Newman produit deux groupes inégaux qui se distinguent par leur centralité de proximité.
La méthode de Clauset et Newman donne trois groupes : un groupe réduit avec peu d’informations, et deux autres groupes qui se distinguent par leur centralité de proximité.
L’algorithme de Louvain affiche également trois groupes déséquilibrés. Les informations dont nous disposons ne permettent pas d’identifier les communautés correspondantes.
Néanmoins, les trois algorithmes précédents présentent des résultats similaires.
La méthode par marche aléatoire, basée sur les chaînes de Markov, identifie quatre groupes. Le 4ème groupe se caractérise par des degrés faibles, donc correspond aux artistes les moins influents. Le groupe 3 regroupe une majorité d’artistes hip hop avec une faible centralité de proximité. En revanche, les genres sont également distribués dans les groupes 1 et 2. 
La méthode optimale, sur les artistes de degré supérieur ou égal à 25, donne quatre groupes équilibrés. Les artistes du groupe 3 sont concentrés sur la période 2015-2017 et ont une faible centralité de proximité. Le groupe 4 présente des caractéristiques musicales particulières, telles qu’une instrumentalité et une acousticité relativement faibles. On peut creuser la piste des communautés fondées sur l’univers artistique. 
Nous avons évalué les algorithmes de clustering avec la mesure de modularité. Plus cette dernière est élevée, plus les groupes sont connectés en interne et séparés entre eux, donc plus l’algorithme est efficace. L’algorithme de clustering spectral présente la meilleure modularité, suivi de l’algorithme de Louvain. 
Une Analyse par Composantes Principales a permis d’identifier les caractéristiques musicales par genre. Le hip hop est caractérisé par un tempo très marqué et une speechiness importante. Le reggaeton, quant à lui, est dansant, énergique et positif. La pop a su se réinventer pour rester le genre populaire par excellence.
