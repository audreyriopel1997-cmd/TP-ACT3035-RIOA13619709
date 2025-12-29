# TP-ACT3035-RIOA13619709
Analyse de données actuarielles

Étape 1 : Acquisition des données
Afin d'acquérir les données que j'ai choisies, j'ai fait ma recherche directement sur Google en recherchant "Jeu de données".
Suite à ma recherche, j'ai choisi le lien "Données ouvertes du Québec" et choisi les dossiers csv afin de pouvoir utiliser dès le départ des bonnes sources.
Je me suis promené dans plusieurs catégories et j'ai enfin choisi le Registre des sanctions administratives pécuniaires environnementalles.
Dans ce registre, nous retrouvons les amendes de non respects de lois au Québec, séparé selon les contrevenants (personnes physiques ou entreprises), les municipalités, l'amende, la date du manquement, le type de manquements et autres catégories que je pourrai trier.
Ce que je trouve intéressant dans ce document, c'est que je pourrai l'analyser de différentes façons. Le but principal sera de démontrer dans quelle municipalité il y a le plus d'amende pour les entreprises.
Selon moi, pour un assureur, l'entreprise qui reçoit des amendes sera une entreprise plus risqué à assurer.

Étape 2 : Processus ETL complet
J'ai ensuite choisi le document le plus recent, donc celui de 2025, jusqu'au 01-12-2025.
Une fois téléchargé, je l'ai renommé "Registre sanction" et enregistré sur mon bureau.
J'ai utilisé read.csv() pour accéder au document sur R que j'ai nommé sanctions.

Afin de commencer mon analyse du document, j'ai utilisé la fonction colnames pour connaitre les types de colonnes ainsi de summary pour mieux visualisé ce qui peut etre utilisé.
Ce qui ressort le plus du summary c'est qu'il y a 765 contrevenants en 2025 et concernant les amendes, le minimum est de 250$, le maximum est de 10 000$ et la moyenne est de 4 327$.
J'ai choisi de garder, la date de saisie, contrevenant, personne_physique, municipalité1 (puisque municipalité2 ce n'est pas au QC), amende et la date du manquement.
Pour faire cette nouvelle table, j'ai du télécharger la bibliothèque tidyverse pour utiliser la fonction sélect.
Ensuite, avec la fonction arrange, j'ai choisi de trier en ordre croissant pour date de saisie et ensuite par personne physique.

Pour la séparation en ensemble de test et d'entrainement, j'ai fait comme vu en classe :
Pour x, j'ai selectionné tout dans la table sauf, amende.
Pour y, j'ai selectionné seulement amende dans ma table.
Puisque j'ai 765 lignes dans ma table, j'ai ajouté n = 765
Toujours comme en classe, j'ai laissé la grandeur de l'échantillon à 80% puisque nous n'avons pas ici d'indication sur le pourcentage.
La longueur de mes données d'entrainement est de 612, ce qui correspond à 80% de 765 et la longueur de mes données test est de 153 correspondant à 20% de 765.

Étape 3 : Analyse exploratoire des données
Voici l'analyse des mesures de tendances centrales de 2025;
Pour l'années, il y a eu au total 3 310 000$ d'amende, l'amende minimale est de 250$ et au maximum de 10 000$. En moyenne, l'amende est de 4326.80$
J'ai recherché sur internet la librarie qu'il me failait pour connaitre le montant de l'amende le plus souvent donné au contrevenant. 
J'ai donc installé la librairie DescTools pour utiliser connaitre le mode qui est de 5 000$.

Concernant les graphiques, le document csv que j'ai choisi pour mon analyse contient qu'une seule variable numérique. 
Il est donc impossible de faire le tableau de correlation. Ce qui en fait un problème concernant le choix des données.
Cependant, j'ai pu analyser deux graphiques différents. Le premier j'ai utilisé Geom_bar afin de demontrer quel type d'amende est le plus frequent ainsi que la pondération de chaque montant d'amende.
Ce qui en ressort le plus c'est que l'amende la plus fréquente est bien 5000$ comme l'indiquait le mode plus haut, ainsi que le minimum de 250$ et le maximum de 10 000$.
J'ai aussi utilisé le geom_boxplot afin de comparer le montant des amendes seulement si c'est une personne physique ou une entreprise.
Ce qui en ressort, c'est que les amendes pour les entreprise sont entre 1 000$ et 10 000$ tandis que pour les personnes physiques c'est entre 250$ et 2 000$ ainsi que quelques 5 000$.

Étape 4 : Définition du problème actuariel
Dans mon model, je n'ai qu'une seule variable numérique, comme indiqué ci-haut. Je n'ai d'autres choix en ce moment que de choisir la variable amende comme variable à prédire.
C'est pourquoi j'ai choisi pour x, tout dans la table sauf, amende et pour y, j'ai selectionné seulement amende.
D'un point de vue actuarielle, il aurait été bénéfique d'avoir plus d'informations sur les personnes ou bien sur les types d'entreprises afin de mieux séparer en catégories.











