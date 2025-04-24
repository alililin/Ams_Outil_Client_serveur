# Ams_Outil_Client_serveur
# Projet de Monitoring Système – L2 S4

Ce projet permet de surveiller l'utilisation des ressources système (RAM, CPU, DISK) et d'alerter automatiquement en cas de situation de crise. Il génère également des graphiques d'historique et les affiche via une interface web.

## Interface Web :
Cette interface web permet de consulter les données des sondes sous forme de graphiques visuels. Elle permet aussi de visualiser les alertes générées par le module de détection de crise.

## Fonctionalités: :
    Affichage des données sous forme de graphiques évolutifs.
    Affichage des alerts.
    Interface de consultation web claire et simple, incluant des graphiques et informations supplémentaires.
    
### Dépendences: 
les éléments sont installés sur le  serveur :

    Python 3 : Langage de programmation utilisé pour le développement de l’interface web.
    Flask : Framework web Python.
    Jinja : Moteur de templates pour Flask.
    BeautifulSoup4 : Pour le scraping de données HTML.
    Requests : Pour effectuer des requêtes HTTP.
    Pygal : Bibliothèque Python pour générer des graphiques interactifs.
    
### Lancement de interface web :
on lance l'application web avec ses commandes suivantes:
  Accédez au dossier où se trouve le fichier app.py : /home/lina/monitoring
  Exécutez l’application Flask : python3 app.py

L’application sera disponible sur l'URL suivante : http://localhost:12345
### Les données utilisées : 
Les données sont stockées dans une base SQLite :  
`/home/lina/monitoring/db/monitoring.db`
Table principale : `system_data`  
- `timestamp`  
- `type` (`RAM`, `CPU`, `Disk`)  
- `value` (en pourcentage)

### Structure des Fichiers
  app.py : Le fichier principal contenant le serveur Flask.
  templates/ : Dossier contenant les fichiers de templates HTML avec Jinja.
  static/ : Dossier contenant les fichiers des graphs (cpu_graph.svg, ram_graph.svg, disk_graph.svg).

### contenue des fichiers
Les scripts codées sont : 
### 1. `generate_graphs.py` – Graphiques historiques
- Récupère les 30 dernières mesures de chaque type.
- Génère un fichier SVG par métrique avec la bibliothèque `pygal`.

### 2. `app.py` – Interface Web Flask
- Affiche les alertes récentes et les graphiques SVG générés.
- Utilise le template HTML `index.html`.
- Lance un serveur web local (`localhost:12345`).



