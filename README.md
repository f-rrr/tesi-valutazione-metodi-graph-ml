# Progetto di Tesi: Valutazione di Metodi di Graph Machine Learning per la Predizione di Interazioni RNA-Malattia

Questo progetto valuta in modo comparativo diversi approcci di graph machine learning per l'analisi di reti biologiche, con particolare attenzione alla predizione di interazioni RNA-malattia.
La ricerca si concentra sul confronto tra diverse architetture di embedding (BioBert, DNABERT-2, OpenAI, LINE, Node2Vec, TransE) attraverso l'analisi prestazionale di algoritmi classici (Alberi Decisionali) vs ensemble (Random Forest) basata su metriche comparative come, ad esempio, l'accuratezza

## Istruzioni per l'Uso

### 1. Configurazione

Modificare `config.json` per impostare:
- `working_dir`: Percorso della directory del progetto
- `nodes_file_path`: Percorso al file TSV dei nodi
- `edges_file_path`: Percorso al file TSV delle relazioni
- `openai_api_key`: La propria API key di OpenAI
