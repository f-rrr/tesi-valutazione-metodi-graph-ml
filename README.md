# Progetto di Tesi: Valutazione di Metodi di Graph Machine Learning per la Predizione di Interazioni RNA-Malattia

Questo progetto valuta in modo comparativo diversi approcci di graph machine learning per l'analisi di reti biologiche, con particolare attenzione alla predizione di interazioni RNA-malattia.
La ricerca si concentra sul confronto tra diverse architetture di embedding (BioBert, DNABERT-2, OpenAI, LINE, Node2Vec, TransE) attraverso l'analisi prestazionale di algoritmi classici (Decision Tree) vs ensemble (Random Forest) basata su metriche comparative come, ad esempio, l'accuratezza

## Istruzioni per l'Uso

### 1. Configurazione
Modificare `config.json` per impostare:
- `working_dir`: Percorso della directory del progetto
- `nodes_file_path`: Percorso al file TSV dei nodi
- `edges_file_path`: Percorso al file TSV delle relazioni
- `openai_api_key`: La propria API key di OpenAI

### 2. Generare Embedding Topologici (LINE, Node2Vec, TransE)
Utilizzare l'embedder nativo per ciascun modello (e la funzione `store_embeddings` presenti nel notebook `specific_edge_prediction.ipynb` per salvare i risultati e poterli riprodurre facilmente).

### 3. Generare Embedding Semantici
- **BioBERT**: eseguire `biobert_embedding_generation.ipynb`
- **DNABERT**: eseguire `dnabert_embedding_generation.ipynb` 
- **text-embedding-3-small (OpenAI)**: eseguire `openai_small3_embedding_generation.ipynb` 

### 4. Concatenazione Embedding
Eseguire `embedding_concatenation.ipynb` per concatenare gli embedding testuali con quelli nativi (LINE/Node2Vec/TransE)

### 5. Predizione e Valutazione
Per i casi di valutazione degli embedding concatenati, caricare il file attraverso la funzione `load_node_embedding` in `specific_edge_prediction.ipynb`
##### Formato File Embedding
Per un corretto caricamento di file esterni:
- Il nome del file deve terminare con `_0` (es: `node2vec_embeddings_0.tsv`) (N.B.: non includere `_0` nel parametro della funzione)
- Struttura file:
  - Prima colonna: `name` (ID dei nodi)
  - Colonne successive: elementi dell'embedding (tipicamente nominate da `0` a `n-1`)

### 6. Visualizzazione Risultati
Utilizzare `create_tables_and_histogram` per generare tabelle comparative in formato latex e reare istogrammi dei risultati - (Sviluppo futuro) Automatizzare l'elaborazione usando il ciclo `for` commentato
Eseguire `overall_best_results` per identificare il modello migliore per ciascuna coppia di tipi
