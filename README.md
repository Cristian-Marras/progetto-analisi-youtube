# Analisi Dati del Canale Youtube Muschio Selvaggio
Progetto universitario di analisi dati sul canale Youtube Muschio Selvaggio. Utilizzando Python e analisi delle metriche di engagement (like, commenti, visualizzazioni, sentiment), si è risposto alla domanda di ricerca: quale conduzione è preferita dal pubblico?

---

## 🎯 Obiettivo del Progetto

L'obiettivo di questa analisi è stato determinare, tramite i dati, quale fase di conduzione del podcast abbia generato maggiore engagement, rispondendo a queste domande chiave:
* Come sono variate nel tempo le metriche di performance (visualizzazioni, like, commenti) e il sentiment del pubblico al cambiare della conduzione?
* Quali sono i video più influenti e centrali all'interno della "rete di discussione" del canale?
* Quali episodi o argomenti creano le maggiori sovrapposizioni di pubblico?
* Come si posiziona il sentiment del canale rispetto a un benchmark di settore (Tintoria Podcast)?

## 📄 Presentazione del Progetto

Per questo progetto è stata preparata anche una presentazione in formato slide, utilizzata per l'esposizione universitaria. Sebbene il report su Deepnote sia più completo e interattivo, è possibile scaricare le slide originali.

* **[Scarica le slide della presentazione (PDF)](./Progetto_SMM_Muschio_Selvaggio.pdf)**

## 🛠️ Strumenti e Tecnologie

* **Linguaggio:** Python
* **Ambiente di Sviluppo:** [Deepnote](https://deepnote.com/) (Piattaforma Cloud per Data Science)
* **Librerie Principali:**
    * **Pandas:** Manipolazione e pulizia dei dati.
    * **NumPy:** Calcoli numerici e statistici (es. CDF/CCDF).
    * **Matplotlib:** Creazione di visualizzazioni.
    * **NetworkX:** Modellazione e analisi di grafi.
    * [**Feel-it**](https://github.com/MilaNLProc/feel-it): Analisi del sentiment sul testo.
    * **`google-api-python-client`:** Interazione con le API di YouTube.
* **Software di Visualizzazione:**
    * **Gephi:** Visualizzazione avanzata di grafi e analisi di base delle reti.
* **Best Practices:**
    * **Gestione Credenziali:** Utilizzo di Environment Variables per la gestione sicura delle chiavi API.
 
## ⚙️ Metodologia e Costruzione del Dataset

L'analisi si basa su un dataset costruito ad-hoc attraverso le API di YouTube e su un grafo di interazione generato a partire dai commenti.

### 1. Data Gathering

* **Selezione Video:** Sono stati raccolti i dati relativi agli **ultimi 100 video** pubblicati sul canale, escludendo gli "Shorts" per mantenere l'analisi focalizzata sui contenuti a lungo formato.
* **Raccolta Commenti:** Per ciascuno dei 100 video, sono stati estratti **200 commenti di primo livello** (escludendo le risposte), per un totale di 20.000 commenti unici analizzati.
* **Metriche Raccolte:** Per ogni video sono state salvate le seguenti metriche chiave: `Titolo`, `Numero di visualizzazioni`, `Numero di like`, `Conteggio dei commenti` e `Data di pubblicazione`.

### 2. Costruzione del Grafo

Per mappare le connessioni e gli interessi del pubblico tra i vari episodi, è stato costruito un grafo non orientato e pesato:

* **Nodi:** Ogni **video** è rappresentato da un nodo nel grafo.
* **Archi (Link):** Un arco collega due nodi (due video) se esiste almeno un utente che ha commentato entrambi.
* **Peso degli Archi:** Il peso di ogni arco è proporzionale al **numero di commentatori unici** che i due video hanno in comune.

Il grafo finale risultante è composto da **100 nodi** e **3112 archi pesati**.
<img src="https://github.com/user-attachments/assets/7cbe11e0-969c-4752-9a0a-05e7f5589b0c" alt="Grafo - una grossa componente connessa" width="60%">

## 🚀 Report Interattivo su Deepnote

Questo repository contiene il codice sorgente dell'analisi. Per una presentazione narrativa dei risultati, con grafici interattivi e spiegazioni dettagliate, si consiglia di visualizzare il progetto direttamente su Deepnote.

* **[Guarda il progetto interattivo su Deepnote](https://deepnote.com/workspace/SMM-3969cef9-ce5a-42de-b779-69673e74d4cc/project/Progetto-SMM-Muschio-Selvaggio-5e5c2b6d-40f0-45a1-af21-5a0dbb73ce96/notebook/Progetto-gathering-1-1cc3dca6c514492a9f570d56a1ff0aaa?utm_source=share-modal&utm_medium=product-shared-content&utm_campaign=notebook&utm_content=5e5c2b6d-40f0-45a1-af21-5a0dbb73ce96)** 

## 📊 Risultati Chiave e Conclusioni

La conduzione originaria del podcast è la più apprezzata dal pubblico secondo quasi ogni metrica analizzata.
<img src="https://github.com/user-attachments/assets/33dc42d9-e4df-463e-860f-250668de1683" alt="Analisi temporale delel visualizzazioni" width="80%">

La seconda fase, nonostante abbia subito un drastico calo di interazione, sembra essere la più apprezzata sotto il punto di vista del sentiment.
<img src="https://github.com/user-attachments/assets/e87e879e-6992-4135-90bb-110b459245dd" alt="Analisi temporale del sentiment" width="80%">

Il sentiment risulta essere in media molto più negativo rispetto a quello del podcast concorrente Tintoria Podcast.
<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/4ad93dc6-f23e-4e9c-99d2-c62c3cb0147c" 
           width="55%"></td>
    <td><img src="https://github.com/user-attachments/assets/80b4ba9f-19e8-48d8-a232-38ffa2516675" 
           alt="Sentiment Tintoria Podcast" width="65%"></td>
  </tr>
</table>



## Contatti

Per qualsiasi domanda o proposta, non esitare a contattarmi:

* **LinkedIn:** [Cristian Marras](https://www.linkedin.com/in/cristian-marras-151932186/)
* **Email:** cristianmarrasj@gmail.com
