# PEIP - Trader

Bienvenu sur le projet trader, dont l'objectif est de répondre à la problématique
suivante : est il possible de s'enrichir avec quelques jeux de données et de l'intelligence artificielle
obtenue sur le web clé en main ?

**Attention, ce projet n'a pas pour objectif de vous pousser à faire du trading, mais plutôt de vous montrer que le trading est généralement est une activité très risquée, entrainant plus de pertes que de gains**. La lecture du livre `The Intelligent Investor, Benjamin Graham, Jason Zweig, Harper Business, février 2006` est conseillée pour compléter vos connaissances liées à ce projet.

Du point de vue compétences, ce projet vous apportera :
- la maitrise du langage Python
- la maitrise de la bibliothèque Pandas
- des connaissances théoriques sur les séries temporelles
- des connaissances sur l'investissement et la spéculation, et leurs risques associés

## Getting started

Les Notebooks vont vous permettre de vous former avant de vous lancer dans votre carrière de trader.

Les données sont stockées dans le dossier `data`.

Pour commencer, il vous suffit de tout importer dans le cocalc de Polytech et de prendre les Notebooks un par un en suivant la numérotation.

Lien vers le Cocalc de Polytech : [Cliquez ici](https://cocalc.polytech.univ-nantes.fr/)

Pour la création de compte sur le Cocalc de Polytech : dbGbLTAbu9TBgLi6

10 séances de projet.

## Stratégies spéculatives

Quelques stratégies de base à tester pour ce projet :
1. Oracle
2. aléatoire
3. [effet janvier](https://en.wikipedia.org/wiki/January_effect)
4. Solution la plus simple "acheter qand le prix est bas, et revendre quand il est haut"
5. quand votre valeur mobilière augmente de X %, allez à la vente. Quand elle redescend de Y %, on rachète
6. moyenne mobile: lorsque le prix est supérieur à la moyenne mobile (moyenne des X dernières valeurs), allez seulement à la vente. Lorsque le prix est inférieur à la moyenne mobile, allez seulement à l'achat.
7. Stratégie [Bourso+](https://www.boursorama.com/bourse/actualites/3-indicateurs-indispensables-de-l-analyse-graphique-fefa599f13e3caffa7135a423c855f69) 

> L'achat est recommandé lorsque la moyenne mobile à 50 jours traverse vers le haut la moyenne mobile exponentielle à 200 jours ;

> La vente est recommandée lorsque la moyenne mobile à 50 jours traverse vers le bas la moyenne mobile exponentielle à 200 jours

7. Relative Strengh Index strategie:
   - [Bourso+](https://www.boursorama.com/bourse/actualites/3-indicateurs-indispensables-de-l-analyse-graphique-fefa599f13e3caffa7135a423c855f69) propose une explication claire
   - https://fr.wikipedia.org/wiki/Relative_strength_index
   - plus détaillée en anglais: https://en.wikipedia.org/wiki/Relative_strength_index
   - acheter quand RSI <= 30 et vendre quand RSI >= 70
8. Donchian channel (https://en.wikipedia.org/wiki/Donchian_channel)
   - la ligne haute est appelée *résistance*
   - la ligne basse est appelée *support*
   - si le prix remonte vers la résistance, il faut acheter
   - si le prix dépasse la résistance, il faut vendre
   - si le prix descend vers le support, il faut vendre
   - si le prix passe en dessous le support, il faut acheter
9. [Kinjun](https://fr.wikipedia.org/wiki/Ichimoku_Kink%C5%8D_Hy%C5%8D)
10. [MACD](https://en.wikipedia.org/wiki/MACD):
    - [Bourso+](https://www.boursorama.com/bourse/actualites/3-indicateurs-indispensables-de-l-analyse-graphique-fefa599f13e3caffa7135a423c855f69) propose une explication claire du MACD
11. Utiliser les variations de **volume** de vente pour déterminer si le produit est survendu/sous vendu

Plus de stratégies simples à tester: regarder les modèles de séries temporelles ARIMA, SARIMAX, ...voir les notebooks "Times Series" associées.

Un autre point à regarder: quel effort nécessite votre stratégie ? combien d'achat / vente sont réalisées ? avez vous essayé d'intégrer un cout de commission pour chaque transaction ?

Envie de faire du réseau de neurones ? de voir d'autres données à prendre en entrée pour vos modèles ? voir les notebooks "Neural Network".

## Stratégies investissement

Plusieurs livres/podcasts conseillent d'investir dans des ETF (Exchange Traded Fund), solution censée être la moins risquée. Selon Chat GPT, un ETF est un fonds d'investissement coté en bourse qui regroupe un ensemble d'actifs (comme des actions, obligations, etc.) et qui réplique la performance d'un indice boursier spécifique.
Par exemple, si vous voulez investir dans les entreprises du CAC40, vous avez deux solutions:
- soit acheter vous même des actions de chaque entreprise appartenant au CAC40 (en mettant à jour en fonction des entreprises qui rentrent or sortent de ce classement)
- soit vous investissez dans un ETF suivant le  CAC40, ce qui semble beaucoup plus simple
L'hypothèse de cette stratégie est que les actions augmentent toujours au fil du temps. Et puisqu'il est impossible de battre le marché, il faut simplement le suivre. Un fond ETF augmenterait ainsi toujours. La stratégie conseillé consiste ainsi à simplement investir régulièrement dans un fond.

Quelques questions:
- quel est le gain est investissant X euros sur un fond ETF - sans rien touché ensuite ? en comparaison avec vos stratégies de trading ?
- quel est serait le gain en investissant X euros par mois dans un ETF ?

## Objectif du projet

Fournir une stratégie présentant une meilleur performance que la stratégie investissement réalisé sur une ETF world. Cette stratégie est déjà implementée dans le notebook `Strategies.ipynb` et testée dans le notebook `ExpInvestStrategy.ipynb`.

Votre stratégie devra bien évidemment fonctionner sur plusieurs jeux de données. Afin de limiter vos tests, voici la liste des jeux de données à tester, à récupérer via la source Google Finance :
- Airbus via Google Finance
- Bitcoin via **CoinCodex**
- NVidia via Google Finance
- Stellantis via Google Finance
- Total via Google Finance
- Credit Agricole via Google Finance

**Attention**, pour les coins, il faut utiliser la source CoinCodex. Pour les valeurs mobilières plus classiques, il faut utiliser la source Google Finance.

Le test devra être réalisé sur les **10 dernières années** du jeu de données de l'ETF World (voir le notebook 07). Il est donc nécessaire de regarder sur quelle période est défini ce jeu de données.

Le jeu sera gagné si en moyenne sur les 6 jeux de données, votre stratégie fait mieux que la stratégie investissement.

## Rendu pour évaluation

Dans votre projet Cocalc :
1. partager votre projet avec `antoine.pigeau@univ-nantes.fr` et `Lynda.Aitoubelli@univ-nantes.fr`
2. créer un dossier `Projet` dans votre projet Cocalc
3. dans le dossier `Projet`:
  - un notebook `Strategies.ipynb` (vos stratégies, implémentant la classe `IStrategy`)
  - un notebook `01-RunTest.ipynb` (code lançant les tests et sauvegardant les résultats des tests dans des fichiers `.csv`)
  - des notebooks `02-DisplayResult[1STRAT..1SERIE].ipynb`, `02-DisplayResult[1STRAT..ALLSERIE].ipynb`, `02-DisplayResult[ALLSTRAT..1SERIE].ipynb`, `02-DisplayResult[ALLSTRAT..ALLSERIE].ipynb`. Le contenu de ces notebooks permet d'analyser les résultats obtenus sur les différentes stratégies et les différentes séries de données. 
  - un dossier `Data` contenant vos données de valeurs mobilières et un dossier `ResultTest` contenant vos fichiers de résultats des tests
4. dans chaque Notebook, indiquez les étudiants ayant participé(e)s à l'implémentation de ce Notebook
5. dans le Notebook `Strategies.ipynb`, expliquez les stratégies implémentées (en donnant un exemple de quand on vend ou quand on achète)
6. dans les Notebooks `02-DisplayResult[_STRAT.._SERIE].ipynb`, ajoutez ensuite des commentaires sur les stratégies (si on gagne ou perd de l'argent, dans quelle condition, nombre de vente/achat à réaliser, prise en compte ou non des frais de trading, ...), des commentaires/explications sur les figures

## Notebook `DisplayResult`

Voici quelques idées de notebooks pour présenter les résultats obtenus sur vos stratégies:
- étude d'une stratégie sur un seul jeu de données
- étude d'une stratégie sur plusieurs jeux de données
- étude de plusieurs stratégies sur un jeu de données
- étude de plusieurs stratégies sur plusieurs jeux de données

Pour le premier, étude d'une stratégie sur un seul jeu de données, un exemple de plan pourrait être :
1. présentation et explication de l'objectif du notebook
2. chargement du jeu de données et du résultat (il est possible de rendre ce point générique, en permettant à l'utilisateur de choisir **le jeu de données** et **la stratégie**)
2. affichage du jeu de données
3. affichage des gains obtenus
4. calculs d'indicateurs (moyenne des gains, écart type, détection des intervalles de dates entrainant une perte ou/et un gain)
5. comparaison des gains avec une méthode de base (la stratégie `Random` par exemple)

Pour le deuxième, étude d'une stratégie sur plusieurs jeux de données, un exemple de plan pourrait être :
1. présentation et explication de l'objectif du notebook
2. chargement des jeux de données et du résultat (il est possible de rendre ce point générique, en permettant à l'utilisateur de choisir **la stratégie**)
2. affichage des jeux de données
3. affichage des résultats obtenus
4. affichage d'un dataframe présentant des indicateurs pour chaque jeux de données (moyenne des gains, écart type, ...)
5. affichage d'indicateurs globaux (gain moyen obtenus sur les jeux de données, écart type, ...)
6. comparaison des gains avec une méthode de base (la stratégie Random par exemple)

Attention, quand vous comparez une stratégie sur plusieurs jeux de données, il peut être intéressant de charger les données sur un même interval de temps. La classe `Loader` permet de réaliser cette tâche (voir la classe et le notebook de test de cette classe).

Pour l'ordre des notebook de visualisation, il pourrait être intéressant de faire une analyse générale des résultats, puis de sélectionner les meilleures stratégies et de faire des analyses plus précises sur celles-ci.

Quelques idées pour améliorer l'affichages des jeux de données et/ou des résultats: 
- afficher sur la série des résultats les intervalles de temps avec des gains négatifs et positifs
- afficher sur la série du jeu de données les moments de vente et d'achat

## Présentation aux départements

Le groupe ?? présentera ses résultats.

Durée de la présentation : 15 minutes de présentation + 10 minutes de questions.

Plan pour la présentation:
1. introduction
    - objectif du projet
    - contexte du projet
    - le trading permet de s'enrichir à tous les coups ?
2. les données utilisées
3. le jeu
    - exemple de trading
    - stratégie oracle/random et évaluation de ces stratégies
    (exemples pour bien comprendre comment sont évalués les stratégies - test sur chaque jour, coût du broker, ...)
4. les stratégies implémentées
5. résultats / démonstration via Notebook
6. conclusion
    - répondre à la question de l'introduction

Merci de m'envoyer les slides de présentation une semaine avant la soutenance.
