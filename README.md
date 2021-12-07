# Analyse de données pour notre TIPE sur les effets de site

## Installation

Modules python :
- `jupyter`
- `obspy` (privilégier conda)

Démarrage :
- `jupyter notebook`

Ajout des données :
- [`1-mise-en-evidence/data/`](1-mise-en-evidence/data/)
    - à partir d'un fichier `.csv` voir [`seismes-template.csv`](1-mise-en-evidence/data/seismes-template.csv) (les données sont téléchargées depuis le RESIF)
- [`2-caracterisation/data/`](2-caracterisation/data/)
    - à partir d'un fichier [`position-nodes.csv`](2-caracterisation/data/position-nodes.csv)
    - dossier `ILLF/` contenant les fichiers `.miniseed`

## Structure

### [Documentation](0-documentation/)

Documentation relative au projet et à l'analyse de données.

- Notebooks outils
- [Lien vers les notes](0-documentation/notes.md)

### [Mise en évidence](1-mise-en-evidence/)

Première partie du projet : mise en évidence des effets de site à l'échelle de l'Alsace.
Utilisation des données déjà récoltées par le RESIF pendant les séismes des 10 dernières années.

- Données se téléchargent
- [Dernier notebook](1-mise-en-evidence/comparaison-stations.ipynb)

### [Caractérisation](2-caracterisation/)

Deuxième partie du projet : mesurer les effets de site à l'échelle d'un site bien particulier, celui de Illfurth avec des données récoltées par des capteurs nombreux et non permanents. Optique de caractériser ce site pour l'utiliser à des fins de prévention (piste de la raisonnance).

- Données récoltées absentes : trop lourdes
- [Dernier notebook](2-caracterisation/caracterisation.ipynb)