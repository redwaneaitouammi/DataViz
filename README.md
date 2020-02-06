# DataViz
Visualization of Australian Fires

 
MOS 5.5 Interactive Data Visualization
 
Subject :  Wildfires of Australia



Ait-Ouammi Redwane
Vaikuntham Ranganath
 
Professeur 
Romain Vuillemot
 
2019 - 2020
 
Collecte et Source de données
	Les nouvelles actuelles sur les feux en Australie se répandent rapidement, mais on ne peut pas en dire autant des données. Les satellites de la NASA fournissent un premier ensemble de données sur les incendies en Australie. 

Sources: https://www.kaggle.com/carlosparadis/fires-from-space-australia-and-new-zeland?fbclid=IwAR0btRqk-fTw1-Ae5Xj7wTABf99LHqtQbmRANsFshZ2oYyE2RE_WKBnbbDk

Possible source pour donnés additionnelle : https://modis.gsfc.nasa.gov/
https://www.google.com/search?q=modis+australia+wildfire&oq=modis+australia+wildfire&aqs=chrome..69i57.8016j0j4&sourceid=chrome&ie=UTF-8


Description du jeu de données
Le jeu de données est sous forme d’une table dont les colonnes sont décritent ci-dessous.

Latitude -Centre d'un pixel de feu de 1 km 
Longitude : Centre d'un pixel de feu de 1 km
Brightness : Température en Kelvin mesuré par l'outil de Channel 21 sur le satellite.
Scan & Track: reflètent la taille réelle des pixels.
Acq_date : date d'acquisition
Acq_time : Temps d'acquisition (en UTC).
Satellite -  Satellite: A = Aqua et T = Terra.
Instrument - Valeur constante pour MODIS.
Confidence (0-100%) : Cette valeur est basée sur un ensemble de quantités d'algorithmes intermédiaires utilisées dans le processus de détection. Elle est destinée à aider les utilisateurs à évaluer la qualité de chaque pixel de hotspot/feu. Les estimations de confiance varient entre 0 et 100 % et se voient attribuer l'une des trois classes d'incendie 
-incendie de faible confiance.
-incendie de confiance nominale.
-incendie de confiance élevée.
Version -  near real time(NRT) ou standard processing.
Bright_t31 - Température en Kelvin mesuré par l”outil de Channel 31 sur le satellite.
Frp-   ‘fire radiative power’ en Megawatts: Représente la puissance radiative du feu intégrée aux pixels 
Daynight - D- Daytime , N- Nighttime

Pour notre analyse on propose d’utiliser seulement quelques colonnes des données qui nous sert. Ce sont les suivantes:

Latitude
Longitude
Brightness ( on choisit le sortie du Channel 21 sur le Channel 31)
Acq_date et Acq_time 
 Frp
Daynight

Questions
	Nous essayerons à implémenter des visualisations qui aideront à répondre à plusieurs questions par analyse des figures à développer on citent: 
Quelles sont  les régions le plus susceptible aux dégât selon les valeurs de FRP (Fire radiative power) qui montre la capacité de dégât du Biomass.
Quelles sont les régions avec des feux le plus forte (avec brightness)
Quel est le corrélation entre le température est le susceptibilité au dégât 
 
Plus loin :
Identifier les tendances pour l’avenir? (peut-être pas possible à répondre)
Quelles sont les causes probable du feu? (besoin de plus de donnés)
Quelles sont les dégâts de Wildlife ( besoin des données de densité du Wildlife selon région)
 
 
Quelques travaux similaires
NYT -  7 images (Page suivante)
https://www.nytimes.com/interactive/2020/01/02/climate/australia-fires-map.html
In real Time 
https://www.rfs.nsw.gov.au/fire-information/fires-near-me
 
 
 
 
 
 
 
 




`

Images:














































Le lien vers le GITHUB: `https://github.com/ranganathvaikuntham/DataViz

Data Cleaning and preparation
Etant donné que le lien de source de nos donnés se compose de quatre base de donnés, on a décidé d’utiliser le premier s’appelle ‘fire_archive_M6_96619.csv’.

Excel est l’outil qu’on emploie pour nettoyer nos donnés. 
Les étapes à suivre pour nettoyer des données avec excel sont le suites:

Comprendre le sense de toutes les colonnes et enlever ce qui nous intéresse pas.
Dans notre cas on enlève les colonnes type ( pas utile pour nous) ,bright_t31 (on utilise déjà le paramètre du ‘brightness’) et version (seulement une valeur pour ce donnes - redondant) .

Exercer la fonction du filtre sur chacun de colonnes pour voir si les valeurs vides existe pour ces colonnes. Si oui, enlève ces lignes.
 Il n’existe pas les cellules vides dans notre donnés, donc pas besoin de modification.

Vérifions s’il existe des données anormaux ou faux. 
Anormaux ou faux donnés sont identifié normalement avec les visualizations exploratives et une compréhension des données. 
Avoir fait quelques visualisations exploratifs on conclure qu'il n’y a pas des données anormaux. En plus le source de NASA est très fiable et réputé. 

Les données sont prêt à télécharger pour le visualization.


D3 and descriptive charts (histogram, scatterplot..).

Histogram max puissance de feu (FRP) et brightness (y-axis) contre le date (x-axis).
 Brightness vs FRP line chart pour voir la corrélation entre les deux. - Pour le couleur a. le satellite b. DayNight (troisième variable).


