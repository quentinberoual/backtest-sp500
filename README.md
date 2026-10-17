# Backtest d'une stratégie de moyennes mobiles sur le S&P 500

Projet personnel de Quentin Beroual, étudiant en 3e année du Programme Grande École de l'ESSCA.

## Objectif
Tester si le croisement des moyennes mobiles à 50 et 200 jours améliore le couple rendement / risque par rapport à un investissement passif dans le S&P 500 (buy & hold).

## Règle de la stratégie
- Moyenne 50 jours au-dessus de la moyenne 200 jours à la clôture : investi le lendemain. Sinon : cash.
- Position décalée d'un jour pour éviter le biais d'anticipation.
- Frais de 0,10 % par transaction, cash non rémunéré.
- Données : Yahoo Finance (^GSPC), cours de clôture quotidiens du 02/01/1990 au 09/10/2026 (9 261 séances).

## Résultats (15/10/1990 – 09/10/2026)

| Indicateur | Stratégie 50/200 | Buy & hold |
|---|---|---|
| Rendement annualisé | 8,3 % | 9,4 % |
| Volatilité annualisée | 13,1 % | 18,0 % |
| Ratio de Sharpe | 0,67 | 0,59 |
| Perte maximale | −33,9 % | −56,8 % |

La stratégie rapporte un peu moins que le marché, mais divise presque par deux la perte maximale et offre un meilleur rendement par unité de risque. Elle protège dans les baisses longues (2000-2003, 2008) et coûte dans les rebonds rapides (2020).

## Contenu du dépôt
- **Notebook Python** (.ipynb) : le backtest complet (pandas, yfinance) et un test de robustesse sur 4 réglages.
- **Fichier Excel** (.xlsx) : le même modèle, entièrement paramétrable.
- **Synthèse PDF** : une page qui résume la méthode, les résultats et les conclusions.

Les résultats Python et Excel sont identiques, ce qui valide le calcul.

## Limites
Indice hors dividendes, exécution supposée au cours de clôture, un seul marché testé.
