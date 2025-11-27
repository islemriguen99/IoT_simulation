# IoT Simulation

## Objectif

Ce projet simule un capteur IoT virtuel qui :
- Envoie des données de température et d’humidité via MQTT.
- Reçoit des commandes descendantes (downlink).
- Affiche un dashboard interactif en temps réel (temp et hum) .

## Étapes pour reproduire la démo

### 1-Installer les dépendances
- Installer la bibliothèque MQTT pour Python : pip install paho-mqtt plotly

### 2-Vérifier le script
Le fichier principal est projetIOwt.ipynb.

Vérifie les paramètres de MQTT websocket client :

Host: broker.hivemq.com
Port: 8884 (WebSocket)
ClientID : client123

### 3-Configurer HiveMQ Web Client
Subscription topic : devices/device123/telemetry
Publish topic : devices/device123/cmd

Etapes : 
1. Ouvrir HiveMQ Web Client
2. Cliquer sur Connect.
3. Ajouter le topic de subscription et cliquer sur Subscribe.
4. Les messages publiés par le script apparaîtront en temps réel dans la section Messages.

### 4️-Lancer la simulation
- Exécuter le script projetIOt.ipynb dans Google Colab.
- Le script publie 10 messages de télémétrie toutes les 2 secondes.
- Les messages apparaissent dans HiveMQ et dans la console du notebook.

### 5-Observer le dashboard
Le graphique Plotly s’affiche avec :

- Température (°C)
- Humidité (%)

Les 20 dernières mesures sont affichées.

### 6-Tester les commandes descendantes
Pour envoyer une commande au capteur virtuel :

1. Aller dans Publish sur HiveMQ Web Client.
2. Topic : devices/device123/cmd
3. Payload exemple : {"led": "on"}
4. Cliquer sur Publish.
5. Le script reçoit et traite le JSON envoyé.

