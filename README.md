# Predikcia diabetu pomocou machine learningu

Projekt z predmetu Strojové učenie na Ekonomickej univerzite v Bratislave. Cieľom je klasifikovať prítomnosť diabetu zo zdravotných a demografických údajov a porovnať viacero algoritmov.

**Nástroje:** Python, pandas, NumPy, scikit-learn, Matplotlib, seaborn, Jupyter Notebook.

## Dáta a postup

Použitý [Diabetes Prediction Dataset](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset) obsahuje 100 000 záznamov. Po odstránení úplne zhodných riadkov zostáva **96 146 záznamov**, z ktorých **8,8 % má diabetes**.

- Čistenie dát, opisná štatistika a vizualizácie súvislostí s diabetom.
- One-hot kódovanie, stratifikované rozdelenie dát v pomere 80 : 20 a normalizácia pre porovnanie modelov.
- Porovnanie logistickej regresie, KNN, lineárneho SVM, Naive Bayes, Decision Tree a Random Forestu s referenčným Dummy modelom.
- Krížová validácia, ladenie KNN a Random Forestu pomocou `GridSearchCV` a vyhodnotenie na testovacích dátach.

Hlavnou metrikou je F1 skóre pre triedu diabetes. Samotná accuracy nestačí: predpovedanie väčšinovej triedy dosahuje približne 91 %, ale nezachytí žiadneho diabetika.

## Výsledky

Random Forest dosiahol najvyššie priemerné F1 v porovnaní modelov. Po ladení dosiahol na testovacích dátach:

| Accuracy | Precision | Recall | F1 |
| ---: | ---: | ---: | ---: |
| 96,9 % | 0,97 | 0,68 | 0,80 |

Podľa dôležitosti premenných v Random Foreste boli najvýznamnejšími vstupmi **HbA1c a glukóza**. Rozdiely medzi skupinami podľa fajčenia nemožno pripísať samotnému fajčeniu bez zohľadnenia veku a ďalších faktorov.
