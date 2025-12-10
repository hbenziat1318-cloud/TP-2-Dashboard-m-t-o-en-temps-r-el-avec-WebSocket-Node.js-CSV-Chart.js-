# TP 2 : Dashboard météo en temps réel avec WebSocket (Node.js + CSV + Chart.js)

```
```
##  Description du projet

Application web de visualisation météorologique en temps réel qui affiche progressivement des données météo via une connexion WebSocket. Le serveur Node.js lit un fichier CSV contenant des données météorologiques et les transmet au client web toutes les 3 secondes, permettant une visualisation progressive des données.

```
```

##  Objectifs pédagogiques

- Créer un serveur WebSocket avec Node.js
- Transformer des données CSV en objets JSON
- Établir une communication bidirectionnelle client-serveur
- Créer des visualisations dynamiques avec Chart.js
- Mettre à jour une interface web en temps réel

##  Technologies utilisées

- **Backend** : Node.js, WebSocket (ws), CSVtoJSON
- **Frontend** : HTML5, CSS3, JavaScript (Vanilla)
- **Visualisation** : Chart.js v2.8.0
- **Utilitaires** : jQuery 3.4.1
- **Serveur HTTP** : Python SimpleHTTPServer ou Live Server

##  Structure du projet

```
meteo-realtime/
│
├── app2.js                 # Serveur WebSocket (port 5002)
├── temp.csv                # Données météorologiques
├── index_tab.html          # Interface client web
├── package.json            # Configuration et dépendances
├── package-lock.json       # Verrouillage des versions
├── README.md               # Documentation du projet
│
└── node_modules/           # Dépendances Node.js (ignoré par Git)

```

##  Installation et exécution

### Prérequis
- Node.js (v14 ou supérieur)
- npm (généralement inclus avec Node.js)
- Navigateur web moderne


### Étapes d'installation

1. **Cloner le dépôt**
   
```bash
git clone https://github.com/hbenziat1318-cloud/TP-2-Dashboard-m-t-o-en-temps-r-el-avec-WebSocket-Node.js-CSV-Chart.js-.git

cd TP-2-Dashboard-m-t-o-en-temps-r-el-avec-WebSocket-Node.js-CSV-Chart.js-
```

2. **Installer les dépendances**
```bash
npm install
```

3. **Lancer le serveur WebSocket** 
```bash
node app2.js
```
> Le serveur WebSocket écoutera sur `ws://localhost:5002`


5. **Ouvrir l'application**
- Naviguez vers `http://localhost:8000` (ou le port utilisé)
- L'interface devrait se charger et se connecter automatiquement au WebSocket

## Fonctionnalités

### Interface utilisateur
1. **Tableau des données** : Affichage progressif des données météo
2. **Graphique des températures** : Courbes pour températures max/min
3. **Graphique des précipitations** : Diagramme à barres pour les jours de pluie

### Flux de données
1. Le serveur lit le fichier `temp.csv`
2. Conversion de chaque ligne en objet JSON
3. Envoi séquentiel au client toutes les 3 secondes
4. Mise à jour en temps réel de l'interface

### Format des données CSV
```csv
mois,tmax,tmin,pluie
Jan,18,8,6
Fev,20,9,5
Mar,23,11,4
...
```

##  Configuration

### Ports utilisés
- **WebSocket** : Port 5002 (modifiable dans `app2.js`)
- **HTTP** : Port 8000 (modifiable selon le serveur utilisé)

### Variables de configuration dans `app2.js`
```javascript
const wss = new WebSocketServer({ port: 5002 }); // Port WebSocket
const interval = 3000; // Intervalle d'envoi (3 secondes)
```

##  Visualisations

### 1. Graphique des températures
- **Type** : Ligne (line chart)
- **Données** : Températures maximale et minimale
- **Couleurs** : Bleu clair (max) et bleu foncé (min)
- **Mise à jour** : Progressive toutes les 3 secondes

### 2. Graphique des précipitations
- **Type** : Barres (bar chart)
- **Données** : Nombre de jours de pluie par mois
- **Mise à jour** : Progressive toutes les 3 secondes

###  Démonstration
<img width="1917" height="975" alt="METEO SCREEN 1" src="https://github.com/user-attachments/assets/2481731f-b0db-49c5-be3a-b4333275f87a" />
<br>

## Réalisation & Auteur
**Réalisée Par :** BENZIAT hana
<br>
**Encadrant par:** Mr.LACHGAR mohammed
<br>
**Date:** 08/12/2025

