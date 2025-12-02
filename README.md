# 🧠 NLP-Projekt: Klassifizierung von Katastrophen-Tweets

Dieses Projekt untersucht, wie gut sich Tweets automatisch in **„Katastrophe“ (1)** oder **„Keine Katastrophe“ (0)** einordnen lassen.  
Der Fokus liegt auf natürlicher Sprachverarbeitung (NLP), Textbereinigung, Feature-Engineering und Modellvergleich im Machine Learning.

---

## 📁 Projektübersicht

Das Ziel:  
Ein ML-Modell entwickeln, das echten Katastrophen-Tweets erkennt und von nicht-kritischen Tweets unterscheidet.

Dafür habe ich:

- den Datensatz bereinigt (NLP Preprocessing)
- die Texte mit **TF–IDF** in numerische Features umgewandelt
- drei Modelle trainiert und verglichen  
- das beste Modell ausgewählt (Logistische Regression)
- Cross-Validation und Hyperparameter-Tuning durchgeführt
- alle Ergebnisse dokumentiert und interpretiert

---

## 📊 Datensatz

**train.csv**  
- **text** → Tweet  
- **target** → 1 = Katastrophe, 0 = keine Katastrophe  
- 7.613 Zeilen, keine fehlenden Werte  

Der Datensatz stammt aus der Kaggle-Competition  
**“Real or Not? Disaster Tweets”**.

---

## 🔧 Verwendete Techniken

### 🧹 1. Text Preprocessing
- Lowercasing  
- Entfernen von Sonderzeichen  
- Tokenisierung  
- Entfernen englischer Stopwords  
- Lemmatisierung (WordNet)  

### 🔠 2. Feature Engineering
- **TF–IDF Vectorizer**  
- Begrenzung auf 5.000 Features  
- Sparse-Matrix-Darstellung  

### 🤖 3. Modelle
Trainiert & verglichen wurden:

| Modell | Accuracy | Stärken |
|-------|----------|---------|
| **Logistische Regression** | **81.88 %** | Sehr balanciert, stabil, ideal für Text |
| **Random Forest** | 80.43 % | Gute Sensitivität, aber weniger präzise |
| **MLP Neuronales Netz** | 81.68 % | Starke Ergebnisse, robust gegen Rauschen |

---

## 🥇 Bestes Modell: Logistische Regression

Die Logistische Regression erzielte die beste Gesamt-Performance:

- **Accuracy:** 81.88 %  
- **Sehr gute Balance** zwischen Precision/Recall  
- Funktioniert besonders gut mit TF–IDF   
- Schnell, interpretierbar und stabil  

### Beispiel aus der Konfusionsmatrix:
- **True Positives (Katastrophe richtig erkannt):** 456  
- **False Negatives (übersehene Katastrophen):** 198  
- **True Negatives:** 791  
- **False Positives:** 78  

---

## 🧪 Validierung & Tuning

### ✔️ 5-fold Cross-Validation  
Ergebnis:  
- Durchschnitts-Accuracy: **70.18 %**  
- Standardabweichung: 3.86 %  

### ✔️ Hyperparameter Tuning (GridSearchCV)
Getestet wurden:  
- Solver: `liblinear`, `lbfgs`  
- Regularisierung `C = [0.1, 1.0, 10.0]`  

**Bestes Setup:**  
- `solver = lbfgs`  
- `C = 1.0`  
→ identische Performance wie Standardparameter, aber bestätigt deren Stabilität.

---

## 📈 Fazit

In diesem Projekt habe ich einen vollständigen NLP-Pipeline-Workflow umgesetzt.  
Ich konnte sehen, wie stark **Preprocessing und Vektorisierung** die Modellleistung beeinflussen und wie unterschiedlich ML-Modelle mit Textdaten umgehen.

**Die wichtigsten Erkenntnisse:**

- Gute Textvorbereitung ist der halbe Erfolg.  
- TF–IDF ist für klassische ML-Modelle eine sehr starke Wahl.  
- Die Logistische Regression liefert eine hervorragende Basis.  
- Modelle sollten immer mit Recall & Konfusionsmatrix bewertet werden – nicht nur mit Accuracy.  
- Komplexere Modelle (MLP, Random Forest) bieten spannende Alternativen, je nach Zielsetzung.  

---

## 🚀 Ausblick

Wenn ich das Projekt erweitern würde:

- Einsatz moderner Embeddings (*Word2Vec, GloVe*)  
- Training eines BERT-Modells (z. B. `bert-base-uncased`)  
- Ausbau zu einer kleinen API, die Tweets live klassifiziert  
- Experimentieren mit Class-Weights, um Klasse 1 (Katastrophen) noch besser zu erkennen  

---

## 💻 Projekt-Notebook und Präsentation

Hier findest du das vollständige Colab-Notebook mit allen Code-Zellen, Auswertungen und Visualisierungen:

👉 **[Klick hier, um das Notebook zu öffnen](https://colab.research.google.com/drive/1FKv3lVJh5tHWga-jMcdc2srv_f7tQZQi?usp=sharing)**  

Und hier findest du die dazu passende Präsentation:

👉 **[Klick hier, um die Präsentation zu öffnen](https://www.canva.com/design/DAG5_OdMV_U/pWaS03bKNLiNdcyLEWRe1Q/edit?utm_content=DAG5_OdMV_U&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)**  

---

## 📬 Kontakt

Wenn du Feedback oder Fragen hast — gerne melden!  
Ich freue mich über Austausch zu NLP, Machine Learning und Data Analytics.
