## 📊 Optimisation de Portefeuille Boursier avec Python 🐍
Bienvenue dans ce projet d'optimisation de portefeuille boursier en utilisant Python. Ce projet a pour but de vous guider dans la création d'un portefeuille d'actions optimisé en maximisant les rendements tout en minimisant les risques. Nous utilisons ici l'API yfinance pour récupérer des données boursières et la théorie moderne du portefeuille (MPT) pour construire un portefeuille optimal.

# 🔧 Technologies Utilisées
Python 🐍
yfinance 📈
pandas 🐼
matplotlib et seaborn 📊
# 🚀 Objectifs du Projet
L'objectif est d'appliquer la théorie moderne du portefeuille afin de construire un portefeuille boursier efficace. Les tâches incluent :
Collecter des données boursières 📉

Visualiser les performances des actions au fil du temps 📆

Calculer les moyennes mobiles et analyser les tendances 📊 

Simuler des portefeuilles aléatoires et tracer la frontière efficiente pour optimiser le portefeuille 🎯
## Analyse 
(regardez main.py pour plus de détails sur le code) 


Pour ce projet, j'ai utilisé l'API yfinance pour télécharger les données de quatre entreprises populaires en Inde (RELIANCE, TCS, INFY, HDFCBANK)

![Capture d’écran 2024-09-06 235233](https://github.com/user-attachments/assets/3eeb48ad-16ab-47aa-8fae-897cf7be5b5c)


Le graphique affiche les prix ajustés de clôture de quatre actions (HDFCBANK.NS, INFY.NS, RELIANCE.NS, TCS.NS) au fil du temps, de septembre 2023 à septembre 2024. Il met en évidence que TCS a les prix ajustés de clôture les plus élevés, suivie de RELIANCE, INFY (Infosys) et HDFCBANK. Les prix de RELIANCE et TCS montrent des tendances haussières marquées, ce qui indique une forte performance, tandis que HDFCBANK et INFY présentent une plus grande stabilité avec des fluctuations de prix relativement faibles.

Passons maintenant au calcul des moyennes mobiles sur 50 jours et 200 jours et à leur tracé en parallèle avec le prix ajusté de clôture pour chaque action :

