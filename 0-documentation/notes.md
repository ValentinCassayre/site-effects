# Notes

## Mise en évidence de l'effet de site

### Données sismologiques

Un capteur sismologique enregristre le sol, la vitesse du sol en chaque point correspond à une donnée, sous forme de vecteurs. 
La fréquence d’échantillonage est le nombre de données par seconde. 
Le format standard international est le format **miniseed**, mais il ne suffit pas à décrire entièrement une donnée.

### Métadonnées

Il manque les métadonnées (informations relatives aux sites) à ces fichiers, pour chaque station. Leur format est celui de **xml**.

### Utilisation

Tous les grands centres de données mondiaux proposent de récupérer les données sous ces formats là.
Il existe une librairie en python qui permet d’analyser ses données **obspy** et permet très facilement de récupérer des données sismologiques et de les enregistrer dans des structures python pour réaliser des opérations simples.
Obspy permet d’interagir avec des *webservices* pour télécharger les données.
On travaille sur le **RLBP (réseau large bande permanent)**.
Les 2 premières lettres correspondent au code du réseau puis il y a le code de la station de 2 à 5 lettres (ex : STR pour Strasbourg ou ILLF pour Illfurth).
Chaque station appartient à un réseau. 
Le **RESIF**, réseau français, permet d’accéder au réseau RLBP.

L' **overall sensitivity** est le gain global du système, il dépend de l’instrument. Il est essentiel et permet de convertir des *counts* en *m/s* (par division).

Les vibrations ambiantes sont de l’ordre du micromètre par seconde (10e-6 m/s).

miniseed = données sous forme de `Trace` ou de `Stream` de `Traces`

xml = `Inventory`

### Application à notre TIPE

Le but est de calculer la **magnitude** “locale” (notée généralement Ml ou Mlv pour verticale) à partir des données des capteurs alsaciens. 
Pour cela on mesure l’**amplitude maximum** de chacun des signaux.
On formate ainsi un tableau avec l'amplitude maximale des signaux pour quelques séismes (assez gros) sur le vertical et la moyenne (géométrique ?) des amplitudes max sur les deux horizontaux.

## Caractérisation de site

Deuxième partie : caractériser un site particulier.

### Date

reporté du 28 au **29 octobre**

### Site

- ~~Strasbourg~~ -> impossibilité de placer les capteurs
- nord de l'Alsace -> loin
- **Illfurth**

### Contraintes

- jusqu’à 5 **rayons** différents (*R1-R5*)
- 5-7 capteurs par rayon

Donc il faut une zone avec environ 400m de rayon autour pour poser les capteurs : problème du capteur de la Rénass (Strasbourg), idéal trouver site entouré de champs.

### Données récoltées

- format miniseed
- taille totale de l'ordre du Go
- 90 traces pour chacun des 30 capteurs 
- environ 40 min de mesure

### Utilisation

regarder des rapports spectraux (faire le spectre de la composante horizontale sur la composante verticale) permet de mettre en évidence des fréquences amplifiées par la structure
appelé **H/V**
lissage de spectre
fmin 1 fmax 50
facteur de lissage 
moyenne géométrique pour la composante horizontale
pics aux alentours des 25 pour 2m de terre, nous décallé vers la gauche