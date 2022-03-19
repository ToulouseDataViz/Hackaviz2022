<!-- author: "Vincent VIVANLOC" -->

<!-- date: "January 2022" -->

<!-- README.md is generated from readme.Rmd. Please edit that file -->

<!-- command: radian then rmarkdown::render("readme.Rmd", encoding = "UTF-8","all") -->

# Hackaviz 2022 : financement par la copie privée en France.

Not speaking french, please find the [english version](README_en.md).

![Mimi and Eunice, [You may be
right](https://mimiandeunice.com/2011/04/08/you-may-be-right/), CC-BY-SA
Nina Paley, mars 2011](images/ME_338_YouMayBeRight2.png)

Nous vous proposons dans un jeu de données inédit issu du site
[AidesCreation.org](http://aidescreation.org/consultation-aides_culturelles_versees_base_actions_soutenues-1.html).
Ce site compile une base de données des financements collectés et
distribués par les [organismes de gestion collective des droits
d’auteur](https://fr.wikipedia.org/wiki/Soci%C3%A9t%C3%A9_de_gestion_des_droits_d%27auteur),
au titre de la rémunération pour [copie
privée](https://fr.wikipedia.org/wiki/Copie_priv%C3%A9e#France).

Ce jeu de données est réparti sur trois fichiers. Il est possible de
faire de belles visualisations à partir d’un seul de ces fichiers. Vous
pouvez aussi les combiner, mais il n’est pas certain que la plus belle
histoire ait besoin de toutes ces données.

Cette année, pas de données géographiques, mais des données à exploiter
sous forme de texte. C’est l’occasion de découvrir le vaste domaine de
l’analyse lexicale ou d’affûter vos meilleurs algorithmes.

Retrouvez les règles et les modes d’évaluation sur la page des [règles de l'Hackaviz](https://toulouse-dataviz.fr/hackaviz/reglement/)
de l’association [Toulouse DataViz (TDV)](http://toulouse-dataviz.fr).

N’hésitez pas à nous contacter sur le
[discord](https://discord.com/invite/RbTR4jKRp9) du Toulouse DataViz
pour discuter entre participants, si vous avez besoin d’aide à propos
des données ou pour rapporter des erreurs dans le jeu de données.

Bonne chance \!

# Description générale des données

Chaque jeu de données est disponible sous forme de deux fichiers, l’un sous
forme de données tabulaires au format
[`.csv`](https://fr.wikipedia.org/wiki/Comma-separated_values) pour
votre outil de traitement de données préféré, et l’autre au format ouvert
[`.xlsx`](https://fr.wikipedia.org/wiki/XLSX) pour Microsoft Excel,
LibreOffice ou votre tableur préféré.

Pour télécharger un fichier de données, placez la souris sur le nom du
fichier, faites un clic droit et choisir “Enregistrer la cible du lien
sous …”.

## Format de fichiers CSV

| Fichier de données                                                                                                                     | Contenu                                                               |
| -------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| [`actions-culturelles-soutenues.csv`](https://github.com/ToulouseDataViz/Hackaviz2022/raw/main/data/actions-culturelles-soutenues.csv) | actions culturelles soutenues par la rémunération sur la copie privée |
| [`agregation_par_organisme.csv`](https://github.com/ToulouseDataViz/Hackaviz2022/raw/main/data/agregation_par_organisme.csv)           | résumé par organisme collecteur et par type d’aide                    |
| [`collecteurs.csv`](https://github.com/ToulouseDataViz/Hackaviz2022/raw/main/data/collecteurs.csv)                                     | descriptif des organismes collecteurs                                 |

Une archive (`.zip`) est aussi disponible pour
[télécharger](https://github.com/ToulouseDataViz/Hackaviz2022/raw/main/data/data.zip)
toutes les données.

- Les fichiers sont encodés en UTF-8.
- Les fichiers `csv` utilisent le séparateur de colonne “`,`” et le
  caractère décimal “`.`”.
- Ces `csv` ont été exportés depuis à un paramètre régional anglais.
  Pensez à modifier les paramètres d’import de votre logiciel préféré
  \!
- Si vous avez des difficultés à importer ces `csv`, nous vous
  proposons une alternative sous forme de fichier au format Microsoft Excel.

## Format de fichiers XLSX

| Fichier de données                                                                                                                       | Contenu                                                               |
| ---------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| [`actions-culturelles-soutenues.xlsx`](https://github.com/ToulouseDataViz/Hackaviz2022/raw/main/data/actions-culturelles-soutenues.xlsx) | actions culturelles soutenues par la rémunération sur la copie privée |
| [`agregation_par_organisme.xlsx`](https://github.com/ToulouseDataViz/Hackaviz2022/raw/main/data/agregation_par_organisme.xlsx)           | résumé par organisme collecteur et par type d’aide                    |
| [`collecteurs.xlsx`](https://github.com/ToulouseDataViz/Hackaviz2022/raw/main/data/collecteurs.xlsx)                                     | descriptif des organismes collecteurs                                 |

## Jointures

- Nous avons pris le soin d’unifier le nom de la colonne `collecteur`
  des fichiers afin que vous puissiez faire des
  [jointures](<https://fr.wikipedia.org/wiki/Jointure_(informatique)>).
- Vous n’avez aucune obligation à fusionner ces fichiers : pensez
  d’abord à l’histoire que vous voulez raconter \!
- Pour joindre deux `csv`, vous pouvez utiliser un modèle
  [ObservableHQ](https://ressources.toulouse-dataviz.fr/newsletter--toulouse-dataviz-15--spcial-hackaviz-2021),
  des librairies comme [python Pandas](https://pandas.pydata.org/) ou
  [R dplyr](https://dplyr.tidyverse.org/reference/mutate-joins.html)
  ou le coder directement.

## Format des valeurs

- Les montants ont été arrondis à l’euro prêt.
- Les dates sont des années au format AAAA.

# Description détaillée des données

## Description du fichier `actions-culturelles-soutenues.csv`

Actions culturelles soutenues par la rémunération pour copie privée

- Ce fichier contient la description de bénéficiaires (auteurs,
  société de production ou tout autre membre de l’organisme
  collecteur), le projet culturel et le montant associé.

- Définitions

  - **Organisme collecteur** : société par laquelle des auteurs
    peuvent gérer les droits d’auteur associés à leur œuvre. En
    centralisant cette gestion, ces sociétés facilitent la collecte
    et le versement des droits d’auteur.
  - **Œuvre** : Une œuvre d’art est une création artistique ou
    esthétique.
  - **Droit d’auteur** : ensemble des droits sur l’utilisation et à
    la diffusion d’une œuvre d’art.
  - **Bénéficiaire** : auteur de l’œuvre d’art ou ses ayants droit :
    éditeur, société de production ou héritiers
  - **Copie privée** : exception au droit d’auteur, qui permet aux
    particuliers de copier des œuvres pour leur usage privé. Une
    part du prix d’un support d’enregistrement ou d’un appareil de
    reproduction de l’œuvre sert à rémunérer les auteurs.

- Notes sur les données

  - Les projets bénéficiaires sont recueillis de l’année 2016 à 2021.
  - Les noms des bénéficiaires ont été consolidés au mieux (exemple:
    les variations `1d Zik`,`1D Zik`,`1D ZIK`,`1D ZIK production`,`1D ZIK prod` sont regroupées sous le nom `1d Zik`)
    mais il est possible qu’il reste des valeurs non consolidées.
  - De la même manière, la description des projets a été consolidée.
  - Les descriptions trop longues peuvent être tronquées.
  - Le règlement de l’Hackaviz stipule qu’il vous est interdit de
    récupérer des données autres que celles fournies : vous pouvez
    vous renseigner sur un chanteur ou une société de production
    pour raconter votre histoire mais vous ne pouvez inclure ni sa
    bibliographie, ni sa discographie dans votre dataviz.

Cette description est disponible sous forme de fichier `.csv`
[meta_actions-culturelles-soutenues.csv](https://github.com/ToulouseDataViz/Hackaviz2022/raw/main/meta/meta_actions-culturelles-soutenues.csv).

| nom colonne  | description                                              | type_valeur          | exemple                                                                           |
| :----------- | :------------------------------------------------------- | :------------------- | :-------------------------------------------------------------------------------- |
| collecteur   | code de l’organisme collecteur sous forme d’acronyme     | chaîne de caractères | SACEM                                                                             |
| annee        | année du projet recevant la collecte des droits d’auteur | entier               | 2017                                                                              |
| aide         | type de soutien                                          | chaîne de caractères | diffusion du spectacle vivant                                                     |
| beneficiaire | nom du bénéficiaire                                      | chaîne de caractères | 03H50                                                                             |
| projet       | description du projet                                    | chaîne de caractères | Tournées et showcases hors France - musiques actuelles et jazz - Marianne Dissard |
| montant      | montant reçu en euros                                    | entier               | 1500                                                                              |
| oeuvre       | type d’oeuvre d’art soutenue                             | chaîne de caractères | Concert                                                                           |

## Description du fichier `agregation_par_organisme.csv`

Résumé par organisme collecteur et par type d’aide, année par année

- Ce fichier contient une ligne pour chaque organisme collecteur et
  pour chaque type d’aide.
- Les colonnes sont, pour chaque année, le nombre de bénéficiaires et
  la somme totale versée.

Cette description est disponible sous forme de fichier `.csv`
[meta_agregation_par_organisme.csv](https://github.com/ToulouseDataViz/Hackaviz2022/raw/main/meta/meta_agregation_par_organisme.csv).

| nom colonne                    | description                                          | type_valeur          | exemple                       |
| :----------------------------- | :--------------------------------------------------- | :------------------- | :---------------------------- |
| collecteur                     | code de l’organisme collecteur sous forme d’acronyme | chaîne de caractères | SACEM                         |
| type_daide                     | type de soutien                                      | chaîne de caractères | diffusion du spectacle vivant |
| nb_aides_2016                  | nombre d’aides délivrées pour l’année 2016           | entier               | 160                           |
| montant_2016                   | montant total en euros des aides délivrées en 2016   | entier               | 1725108                       |
| nb_aides_2017, montant_2017, … | idem pour les années suivantes                       |                      | 223                           |

## Description du fichier `collecteurs.csv`

Description des organismes collecteurs

- Ce fichier contient la description des organismes collecteurs.
- Les membres d’un organisme sont les artistes couvertes par cet
  organisme. Ils sont classés par ordre alphabétique et sont séparés
  par une virgule.

Cette description est disponible sous forme de fichier `.csv`
[meta_collecteurs.csv](https://github.com/ToulouseDataViz/Hackaviz2022/raw/main/meta/meta_collecteurs.csv).

| colonne          | description                                          | type_valeur          | exemple                                                                                  |
| :--------------- | :--------------------------------------------------- | :------------------- | :--------------------------------------------------------------------------------------- |
| collecteur       | code de l’organisme collecteur sous forme d’acronyme | chaîne de caractères | SACEM                                                                                    |
| libelle          | nom complet de l’organisme                           | chaîne de caractères | Société Des Auteurs, Compositeurs Et Éditeurs De Musique                                 |
| œuvre            | type d’œuvre d’art couvert par l’organisme           | chaîne de caractères | Musique                                                                                  |
| date_creation    | année de création de l’organisme                     | entier               | 1851                                                                                     |
| membres          | artistes ou producteurs membres de l’organisme       | chaîne de caractères | arrangeur,auteur,auteur de doublage sous titrage,auteurs réalisateur,compositeur,éditeur |
| nb_membres       | nombre de membres                                    | entier               | 182520                                                                                   |
| nb_membres_annee | année où ce nombre de membres a été relevé           | entier               | 2021                                                                                     |
| URL              | adresse du site Internet                             | chaîne de caractères | <https://www.sacem.fr/>                                                                  |

# Sources des données

- Les données issues du site
  [AidesCreation.org](http://aidescreation.org/consultation-aides_culturelles_versees_base_actions_soutenues-1.html).
- Ce site est édité par l’association [“la Culture avec la Copie
  privée”](https://www.copieprivee.org) qui a pour but de promouvoir
  la rémunération par la copie privée. La directrice de publication
  n’est autre que la présidente d’un des organismes collecteurs
  (SOFIA). Enfin, cette association a pour membres, les 17 organismes
  collecteurs qui alimentent la base de données.

# Historique des versions

- Décembre 2021: consolidation des fichiers et génération du readme et
  export sous R et Visual Studio Code

# Conditions générales d’utilisation

- Ce jeu de données est proposé par l’association Toulouse DataViz
  dans le cadre du concours Hackaviz afin de promouvoir la
  visualisation de données. Ce jeu de données est utilisé à des fins
  pédagogiques en permettant aux participants de créer leurs
  visualisations.

- Les données sources proviennent d’organisations officielles qui les
  publient sur Internet sans licence connue. Ces données, énumérées
  dans la section précédente, ont été traitées par l’équipe de
  l’association Toulouse Dataviz pour enrichir leur contenu
  informationnel. L’association Toulouse Dataviz ne saurait garantir
  l’exactitude, la complétude et l’actualité ni des jeux de données
  sources ni des traitements effectués sur ces données.

- Les visualisations produites à l’issue de ce concours en temps
  limité n’engagent pas la responsabilité de l’association Toulouse
  Dataviz.

- Le jeu de données est à l’usage exclusif de l’Hackaviz. Pour toutes
  autres utilisations, veuillez contacter l’association Toulouse
  Dataviz.
