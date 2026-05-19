# 🪙 Bitcoin Trading Signal Classification: 1-Minute Historical Data

Questo archivio contiene il codice e l'analisi per un modello di classificazione volto a prevedere i segnali operativi di trading (**Buy / Sell**) sul Bitcoin. L'analisi si basa sul comportamento dei prezzi nel breve periodo rispetto al lungo periodo.

## 📊 Dataset e Gestione Big Data
A causa delle dimensioni elevate del file sorgente (**515,8 MB**), in linea con le best practice di sviluppo e gestione dei Big Data, il dataset non è caricato direttamente su questa repository GitHub ma è ospitato su uno storage cloud dedicato.

Il dataset originale contiene i dati storici storici minuto per minuto (intervallo di 1 minuto) provenienti da **Bitstamp**, uno dei più grandi siti di scambi di Bitcoin al mondo per volume medio giornaliero.

* **File originale:** `btcusd_1-min_data.csv` (515,8 MB)
* **Fonte dati:** Bitstamp (Dati storici Bitcoin)

### 📥 Download del Dataset
È possibile scaricare il file CSV completo cliccando sul badge sottostante:

[![Google Drive](https://img.shields.io/badge/Dataset-Scarica%20da%20Google%20Drive-blue?style=for-the-badge&logo=googledrive&logoColor=white)](https://drive.google.com/file/d/1Wl2Zol_GS6Oz3Itg_QwdtbYbs-BNM7JQ/view?usp=drive_link)

---

## 🎯 Obiettivo della Ricerca
L'obiettivo di questo caso di studio è addestrare e valutare un modello basato sulla classificazione per prevedere se il segnale corrente è di **acquisto (1)** o **vendita (0)** a seconda del prezzo a breve termine rispetto a quello a lungo termine. 

Prevedere un segnale di trading in un quadro di classificazione rappresenta una componente fondamentale per lo sviluppo di strategie di trading quantitative e algoritmi automatizzati.

---

## 🛠️ Pipeline di Preprocessing & Pulizia Dati
Il dataset è stato sottoposto a una fase intensiva di pulizia ed ingegneria delle caratteristiche prima della modellazione:
1.  **Rimozione del Rumore:** Eliminazione dei minuti in cui non sono state effettuate transazioni finanziarie (volumi a zero) o in cui il prezzo è rimasto completamente costante. Questo processo riduce drasticamente i falsi segnali ed evita che il modello confonda il rumore di fondo con reali trend di mercato.
2.  **Feature Engineering:** Calcolo e confronto delle metriche di prezzo a breve termine rispetto a quelle a lungo termine per generare la variabile target binaria (Label `1` per Buy, `0` per Sell).

---

## 💻 Tecnologie e Modelli Utilizzati
Il progetto è stato sviluppato interamente in ambiente **Python** sfruttando le librerie standard della Data Science:

* **Pandas & NumPy:** Per la manipolazione e pulizia delle strutture dati ad alta densità.
* **Scikit-Learn:** Per la costruzione del modello predittivo.
* **Modello di Machine Learning:** È stato implementato e ottimizzato un algoritmo di **Albero Decisionale (Decision Tree Classifier)**, scelto per la sua interpretabilità e capacità di catturare relazioni non lineari tra le feature di prezzo.

---

## 🚀 Come eseguire l'analisi sul tuo computer

1. **Clona la repository:**
   ```bash
  git clone https://github.com/usema07/bitcoin-classification-machine-learning.git
cd bitcoin-classification-machine-learning
