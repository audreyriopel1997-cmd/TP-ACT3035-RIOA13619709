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



