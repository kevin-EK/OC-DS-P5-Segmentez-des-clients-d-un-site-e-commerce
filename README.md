# OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce
Aider les équipes d'une société brésilienne à comprendre les différents types de leurs utilisateurs, en utilisant donc des méthodes non supervisées afin de créer des regroupement de clients au profils similaires.

## I. Contexte et Problématique

  _ Olist est une entreprise brésilienne qui propose une solution de vente sur les marketplaces en ligne.
  _ Elle souhaite comprendre les différents types d'utilisateurs grâce à leur comportement et à leurs données personnelles.
  _ Otis souhaite fournir à ses équipes d'e-commerce cette segmentation de clients qu’elles pourront utiliser au quotidien pour leurs campagnes de communication.
  _ Mon rôle est de leur fournir une description actionnable de segmentation et de sa logique sous-jacente pour une utilisation optimale, ainsi qu’une proposition de contrat de maintenance basée sur une analyse de la stabilité des segments au cours du temps. 

## II. Descriptifs des Données
![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/e2d51a70-78b7-41c5-a480-dc01fe194928)
  - 9 fichiers « .csv »
  - Merge et groupby pour obtenir data frame « clients »
  - 99441 commandes pour 96096 clients uniques
  - Seulement 3.12% des clients ont commandés plus d'une fois sur le site.
  - 97% des commandes ont été livrés et 1,24% des commandes ont été annulées ou sont indisponibles (donc supprimées de notre data frame)


## III. Analyse RFM
![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/df0fdfb8-492e-43c8-8284-7d5ec37b7b96)

## IV. Comparaison des méthodes de Clustering
  #### A). CAH meilleur segmentation k=2
    ![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/a7491fe5-755b-460c-b974-ed2ac477bcdb)
    ![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/32d86541-3e92-4a69-aab9-837d43811438)

  Visualisation grâce APC segmentation CAH
    ![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/d6bc156b-c0f7-4ecd-a890-6c9a72cb190b)

  Analyse résultat
  ![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/4eb115b9-9f48-4896-a328-90e66d7b73e0)

  Le premier segment est composé des clients qui en moyenne:
    - Sont un peu moins ancien que ceux du segment 2
    - achètent plus de 2X plus souvent et 2X plus d’article que ceux du segment 2
    - Commandent pour 300 real vs 164 real pour le groupe 2

    ![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/719733d2-f618-476b-bc89-873d8a93e3fe)

    
  #### B). K-means meilleur segmentation k=6
    ![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/fb9ec90e-c873-45df-95d7-1b297c8e6e36)
    ![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/2e80d3c2-a74a-4d73-a069-3953f3981efb)
    
    Analyse résultat
    ![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/f6024b7d-343d-4e95-9da0-23a5e59524b6)

  - Gp1 : Anciens Clients qui ont acheté qu’1 fois 1 article pour un montant moyen de 131 Real 
  - Gp2 : groupe de client qui dépense le plus 1257 real en moy.
  - Gp3 : Segment des clients les plus fidèles (2 fois en moyenne) qui achète 2,5 articles par commande
  - Gp4 : Segments de clients qui achète le plus d’article  par commande en moy. env.4 article
  - Gp5 :  Groupe des nouveaux clients. Ils dépense le moins sur le site et sont les plus content de leur achat
  - Gp6: Groupe de client mécontent de leur achat.

    ![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/1d7727ee-520f-46b2-875c-76794c0749ed)

  #### C). DBSCAN 
      Analyse résultat
      /!\ Le DBSCAN a créé un groupe unique et ne permet pas de segmenter la base des clients

  #### D). Conclusion 
    - Le CAH Propose une segmentation en 2 groupes, les clients les plus récent qui ont acheté plus d’une fois et ceux qui dépensent beaucoup vs les mauvais clients ceux du groupe 2.
    - L’algorithme de DBSCAN ne permet pas de segmenter la base de données clients.
    - La meilleure méthode de clustering est le k-means qui propose 6 groupes homogènes de clients. Elle est plus stable (même résultat malgré les diff itérations        contrairement au CAH)

## V. Analyse de stabilité dans le temps & Proposition de contrat de maintenance
  On s’aperçoit qu’au bout de 3 mois, le Ajusted Rand Score chute brutalement.
  Donc on propose de relancer la segmentation tous les 3 mois

  ![image](https://github.com/kevin-EK/OC-DS-P5-Segmentez-des-clients-d-un-site-e-commerce/assets/69479292/8f6435d3-d1c4-4da7-ae79-f8b358ce5f68)






