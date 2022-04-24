# Analyse des ventes d'une librairie et recherche de corrélations
 
Projet Openclassrooms formation data Analyst  


## Code Preparation   

Utilisation des librairies : Numpy, Pandas, Matplotlib et Seaborn  

3 datasets (customers, products, transactions)  
Pour chaque dataset :  
- Vérification unicité, valeurs nulles, doublons  
- Vérification distribution univariée, outliers  

Nettoyage des données :  
- Mise de côté des tests
- Séparation des timestamps pour extraire les dates  

Réalisation de la jointure

Mise de côté des transactions sans prix/catégories  

Vérification des clients/produits sans transactions  

Enregistrement du fichier de travail  


## Code Analyses 01    

Utilisation des librairies : Numpy, Pandas, Matplotlib et Seaborn 

### Etude du CA :  

Calcul du CA total : 11,853,728.68 €  
Représentation de l'évolution du CA dans le temps 

Analyse de la baisse du CA en 10/2021  
Représentation de l'évolution du CA dans le temps par catégorie de livres  
-> Problèmes de ventes de produits catégorie 1 en 10/2021  

### Etude des produits :  

Analyse des produits les plus et moins vendus  
Répartition des ventes par catégorie de livres  

### Etude des clients :  

Analyse de la répartition du CA par clients (courbe de Lorenz et indice de Gini)  
Top 10 des plus gros acheteurs (en CA)  

Analyse de la répartition des ventes par clients (courbe de Lorenz et indice de Gini)  
Top 10 des plus gros acheteurs (en nombre de ventes)  


## Code Analyses 02  

Utilisation des librairies : Numpy, Pandas, Matplotlib, Seaborn, Scipy et Statsmodel 

Mise de côté des gros acheteurs  

### Etude corrélation entre genre des clients et catégories de livres :  

Test chi2 sur les clients uniques  
Test d'ANOVA sur toutes les transactions 
-> Pas de corrélations 

### Etude des corrélations liées à l'âge des clients :  

Vérification de la distribution de l'âge des clients -> verifier normalité (test Shapiro-Wilk, d'Agostino et Anderson-Darling)  
-> Rejet de l'hypothèse de normalité, utilisation de tests non paramétriques  

Age des clients et montant total des achats  
Test Spearman et Kendall : présence d'une corrélation  

Age des clients et fréquence d'achats (sur le nombre de ventes et les sessions de ventes)   
Test Spearman et Kendall : présence d'une corrélation  

Age des clients et taille du panier moyen    
Test Spearman et Kendall : présence d'une corrélation 

Age des clients et catégories de livres achetés  
Test Kruskal-Wallis : présence d'une corrélation  

### Etude de la probabilité d'achat 0_525 sachant 2_159 : 

Reprise des données originales (avec les 4 clients mis de côtés)  
Calcul de la probabilité qu'un client achète la référence 0_525  
Calcul de la probabilité qu'un client achète la référence 2_159  

Calcul P(A inter B) : probabilité qu'un client achète les deux références  
-> Même nombre de clients. Tous les clients ayant acheté 0_525 ont également acheté la référence 2_159  
-> Environ 86.6% de chances qu’un client ayant acheté la référence 2_159 achète également la référence 0_525. 




