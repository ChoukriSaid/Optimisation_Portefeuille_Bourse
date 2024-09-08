## 📊 Optimisation de Portefeuille Boursier avec Python 🐍
Bienvenue dans ce projet d'optimisation de portefeuille boursier en utilisant Python. Ce projet a pour but de créer un portefeuille d'actions optimisé en maximisant les rendements tout en minimisant les risques. J'utilise ici l'API yfinance pour récupérer des données boursières et la théorie moderne du portefeuille (MPT) pour construire un portefeuille optimal.

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
## Analyse et discussions
(regardez main.py pour plus de détails sur le code) 


Pour ce projet, j'ai utilisé l'API yfinance pour télécharger les données de quatre entreprises populaires en Inde (RELIANCE, TCS, INFY, HDFCBANK)

![Capture d’écran 2024-09-06 235233](https://github.com/user-attachments/assets/3eeb48ad-16ab-47aa-8fae-897cf7be5b5c)


Le graphique affiche les prix ajustés de clôture de quatre actions (HDFCBANK.NS, INFY.NS, RELIANCE.NS, TCS.NS) au fil du temps, de septembre 2023 à septembre 2024. Il met en évidence que TCS a les prix ajustés de clôture les plus élevés, suivie de RELIANCE, INFY (Infosys) et HDFCBANK. Les prix de RELIANCE et TCS montrent des tendances haussières marquées, ce qui indique une forte performance, tandis que HDFCBANK et INFY présentent une plus grande stabilité avec des fluctuations de prix relativement faibles.

Passons maintenant au calcul des moyennes mobiles sur 50 jours et 200 jours et à leur tracé en parallèle avec le prix ajusté de clôture pour chaque action :




![Capture d’écran 2024-09-07 144717](https://github.com/user-attachments/assets/7f967bc3-3685-41ae-88dd-fe9f458d2de0)






![Capture d’écran 2024-09-07 144742](https://github.com/user-attachments/assets/48c3f04e-c931-4ba4-813d-d2756e1a7194)


![Capture d’écran 2024-09-07 144757](https://github.com/user-attachments/assets/7dc11981-6f75-438d-ad4b-bbb2e6a3d929)




![Capture d’écran 2024-09-07 144812](https://github.com/user-attachments/assets/71b945de-8daf-4663-af50-2f579da8a9ae)

Pour HDFCBANK et INFY, les prix diminuent initialement mais montrent ensuite des signes de reprise, comme l'indiquent les moyennes mobiles. RELIANCE et TCS affichent une tendance haussière plus régulière dans leurs prix ajustés de clôture. Les graphiques de volume des transactions mettent en évidence une activité de trading significative à différents moments, avec des pics indiquant des volumes de transactions élevés, particulièrement visibles pour HDFCBANK et RELIANCE au début de 2024. Ces informations sont essentielles pour comprendre les mouvements de prix et les comportements de trading, ce qui aide à prendre des décisions d'investissement éclairées.

Voyons maintenant la distribution des rendements quotidiens de ces actions :



Les distributions sont approximativement normales, centrées autour de zéro, ce qui indique que la plupart des rendements quotidiens sont proches du rendement moyen. Cependant, il y a des extrémités des deux côtés, reflétant des gains ou des pertes significatifs occasionnels. INFY et RELIANCE semblent avoir des distributions légèrement plus larges, ce qui suggère une plus grande volatilité comparée à HDFCBANK et TCS.

Voyons maintenant s'il existe une corrélation entre ces actions :
![Capture d’écran 2024-09-07 145439](https://github.com/user-attachments/assets/5eb5837a-c0ef-465d-bab9-a3092d4aff8a)

INFY et TCS ont une forte corrélation positive (0,71), ce qui indique qu'elles ont tendance à évoluer dans la même direction. HDFCBANK a une corrélation positive modérée avec RELIANCE (0,32) et une faible corrélation avec INFY (0,17) et TCS (0,10). RELIANCE présente une faible corrélation avec INFY (0,19) et TCS (0,08). Ces corrélations variables suggèrent des avantages potentiels en termes de diversification ; combiner des actions avec de faibles corrélations peut réduire le risque global du portefeuille.

## Optimisation de Portefeuille
En utilisant la Théorie Moderne du Portefeuille, nous pouvons construire un portefeuille efficace en équilibrant le risque et le rendement. Voici les étapes :

  *Calculer les rendements attendus et la volatilité pour chaque action.

  *Générer une série de portefeuilles aléatoires pour identifier la frontière efficiente.

  *Optimiser le portefeuille pour maximiser le ratio de Sharpe, une mesure du rendement ajusté au risque.

  *Commençons par calculer les rendements attendus et la volatilité pour chaque action :

![Capture d’écran 2024-09-08 182125](https://github.com/user-attachments/assets/6ccbdea9-463e-4eb0-9fd9-e56e4980b0e3)



INFY a le rendement le plus élevé (31.76 %) et une volatilité modérée (22.28 %), ce qui indique un investissement potentiellement très rémunérateur avec un risque relativement élevé. RELIANCE et TCS ont également des rendements attendus élevés (respectivement 20.30 % et 29.74 %) avec une volatilité modérée (21.46 % et 20.77 %). HDFCBANK affiche le rendement attendu le plus faible (4.11 %) et une volatilité modérée (21,69 %), ce qui en fait l'option la moins attractive en termes de rendement ajusté au risque.

Ensuite, nous allons :

  *Générer un grand nombre de pondérations de portefeuilles aléatoires.

  *Calculer le rendement attendu et la volatilité pour chaque portefeuille.

  *Tracer ces portefeuilles pour visualiser la frontière efficiente.

Commençons par générer les portefeuilles aléatoires et tracer la frontière efficiente :

![Capture d’écran 2024-09-08 182431](https://github.com/user-attachments/assets/6be7697e-2b93-4882-a695-d7d18bf373fb)

Chaque point représente un portefeuille, avec la couleur indiquant le ratio de Sharpe, une mesure du rendement ajusté au risque. Les portefeuilles situés sur le bord gauche de la frontière (plus près de l'axe des y) offrent les rendements attendus les plus élevés pour un niveau de volatilité donné, ce qui représente des portefeuilles optimaux. Le dégradé montre que les portefeuilles avec des ratios de Sharpe plus élevés (bleu plus foncé) offrent de meilleurs rendements ajustés au risque.

Le portefeuille avec le ratio de Sharpe maximal présente les caractéristiques suivantes :

![Capture d’écran 2024-09-08 182745](https://github.com/user-attachments/assets/93e1858c-bcce-465f-b2dd-d3896e96b4f5)

  Rendement attendu : ~27.45 %
  
  Volatilité : ~16.48 %
  
  Ratio de Sharpe : ~1,66
  
Passons maintenant à l'identification des pondérations des actions dans le portefeuille qui génèrent le ratio de Sharpe maximal :

![Capture d’écran 2024-09-08 182921](https://github.com/user-attachments/assets/22a586e5-178c-4345-a60b-d788408a2141)


Le résultat montre un portefeuille diversifié avec les allocations suivantes :

  HDFCBANK : 28.15 %
  
  INFY : 24.56 %
  
  RELIANCE : 26.89 %
  
  TCS : 20.38 %
  
Cette allocation équilibrée vise à maximiser les rendements tout en minimisant le risque, en tirant parti des performances individuelles des actions et de leurs corrélations.

## Conclusion
Ainsi, c'est ainsi que fonctionne l'optimisation d'un portefeuille boursier. L'optimisation d'un portefeuille boursier implique l'analyse des tendances des prix, le calcul des rendements et des volatilités attendus, ainsi que la détermination des corrélations entre différentes actions pour obtenir une diversification.




























