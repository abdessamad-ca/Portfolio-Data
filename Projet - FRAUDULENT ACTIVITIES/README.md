# <H1 align="center">FRAUDULENT ACTIVITIES</H1>

![](https://github.com/abdessamad-ca/Portfolio-Data/blob/master/Projet%20-%20FRAUDULENT%20ACTIVITIES/10.jpg)

<H2 align="center">Introduction</H2>

**L'entreprise X fait du E-commerce et vend des vêtements faits-main. Votre but est de construire un modèle qui permette de prédire si l'achat d'un vêtement doit être considéré comme une transaction frauduleuse ou non.
Voici précisément ce que vous devez faire :**

* Pour chacun des utilisateurs, déterminez le pays d'origine depuis son adresse IP

* Construisez un modèle qui permette de prédire si l'activité est frauduleuse ou non. Expliquez aussi vos choix / hypothèses en termes d'optimisation de faux-positifs et faux-négatifs

* Votre patron aimerait comprendre votre modèle car il est inquiet d'utiliser un modèle black box. Comment l'expliqueriez vous d'un point utilisateur, et non pas mathématique. Par exemple, quels sont les utilisateurs qui peuvent être classés comme risqués ?

* Supposons que vous pouvez utiliser votre modèle en live pour qu'il fasse sa prédiction en temps réel. D'un point de vue Produit, comment l'utiliseriez-vous ? Comment pourriez-vous penser l'expérience utilisateur face à ce produit 



## <H2 align="center">Exploratory Data Analysis</H2>

![](https://github.com/abdessamad-ca/Portfolio-Data/blob/master/Projet%20-%20FRAUDULENT%20ACTIVITIES/3.png)


Après une analyse exploratoire sur les données, j'ai constaté que 9,36% des transactions étaient frauduleuses. 
La valeur moyenne des achats frauduleux est de 36 $, tandis que l'âge moyen d'un utilisateur qui commet une fraude est de 33 ans

<H3 align="center">IP Addresses and Countries</H3>

La première tâche de mon analyse a été de mapper l'adresse IP de chaque utilisateur à son pays d'origine, en utilisant les données des deux tableaux. J'ai vérifié chaque adresse IP par rapport aux limites inférieure et supérieure pour chacune des 140 000 bandes IP afin de faire correspondre chacune à un pays. Il s'agissait d'un processus lent en termes de calcul, mais pourrait probablement être grandement amélioré à l'avenir en utilisant des tables de hachage. De toutes les adresses IP correspondantes, environ 22 000 provenaient d'un pays «inconnu». Avec environ 14 000 transactions frauduleuses, 10 pays représentaient 80% de toutes les fraudes. 39% des événements frauduleux provenaient d'adresses IP aux États-Unis et 13% d'un pays «inconnu».

![](https://github.com/abdessamad-ca/Portfolio-Data/blob/master/Projet%20-%20FRAUDULENT%20ACTIVITIES/7.png)
![](https://github.com/abdessamad-ca/Portfolio-Data/blob/master/Projet%20-%20FRAUDULENT%20ACTIVITIES/6.png)

<H2 align="center">Feature Engineering</H2>


![](https://github.com/abdessamad-ca/Portfolio-Data/blob/master/Projet%20-%20FRAUDULENT%20ACTIVITIES/8.png)

feature `time_to_purchase` en prenant la différence entre` purchase_time` et `signup_time` pour voir si cela était corrélé à la fraude, et, voilà, 56% des transactions frauduleuses ont eu lieu dans un délai de 5 jours entre l'inscription et l'achat . La durée moyenne de l'achat était de 57 jours avec un écart type de 36 jours. Avec 62% des fraudes survenant à un écart-type inférieur à la moyenne, cela semble être un indicateur fort de fraude.
</br>
</br>
Le sexe d'un utilisateur n'indiquait pas de fraude, les hommes représentant 58% de la population d'utilisateurs et 59% des transactions frauduleuses




## <H2 align="center">Conclusion</H2>

![](https://github.com/abdessamad-ca/Portfolio-Data/blob/master/Projet%20-%20FRAUDULENT%20ACTIVITIES/2.png)

![](https://github.com/abdessamad-ca/Portfolio-Data/blob/master/Projet%20-%20FRAUDULENT%20ACTIVITIES/1.png)


##### On souhaite à tout prix éviter les achats frauduleux. Pour cela, on doit donc limiter au maximum les faux négatifs.
##### 
##### Voici quelques axes d'amélioration pour améliorer notre modèle de prédiction :
##### 
##### Un système de black-list permettant de bannir les utilisateurs ayant réalisé des achats frauduleux. En effet, en parcourant les données du dataset, on se rend compte que certains fraudeurs réalisent plusieurs achats à partir du même devide_id et de la même ip_address
##### Ajouter de nouvelles variables explicatives à notre dataset afin de permettre à notre modèle de reconnaitre les cas de fraude restants
##### **




