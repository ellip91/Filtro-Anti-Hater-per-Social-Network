In questo progetto si va a  costruire un modello in grado di filtrare i commenti degli utenti in base al grado di dannosità del linguaggio.

PREPROCESSING:
-Effettuo il preprocessing:
Definisco la funzione preprocess_text. Questa funzione esegue la rimozione di punteggiatura, conversione a minuscolo, tokenizzazione, rimozione delle stopwords e lemmatizzazione.
-Separo le features dalle label: Separo i commenti preprocessati (X) dalle etichette (y)
-Divido il dataset in train e test: Utilizziamo train_test_split per dividere il dataset in dati di training e di test. 

CREAZIONE DEL MODELLO:
Inizio con l'addestramento e la valutazione di due modelli più semplici per la classificazione di testi: la regressione logistica e il Naive Bayes. Nel primo caso utilizzo LogisticRegression con il parametro class_weight='balanced' in quanto abbiamo sbilanciamento di classi. Nel caso sei Naive Bayes addestro diversi modelli per vedere quale performa meglio. In entrambi i casi, trasformo i testi in feature numeriche tramite TfidfVectorizer. Inoltre, tramite OneVsRestClassifier adatterò modelli di classificazione binaria a problemi di classificazione multilabel. Le Metriche da tenere in considerazione per la valutazione del modello sono l'F1-score, la precisione e il recall, più appropriate perché tengono conto dello sbilanciamento delle classi e della natura multilabel del problema.
La regressione Logistica performa meglio del naive Bayes in questo problema di classificazione multilabel ma le metriche non sono ancora ottimali. Testo allora l'utilizzo delle reti neurali ricorrenti, adatte a questo tipo di problemi.

Per la RNN eseguo un ulteriore preprocessing del dataset:

Tokenizzazione e Padding: I testi vengono tokenizzati e trasformati in sequenze di numeri interi e di lunghezza uniforme.
Per la costruzione del modello creiamo una RNN che utilizza strati LSTM mentre l'output utilizza l'attivazione sigmoid per gestire la classificazione multilabel. Sia per Early Stopping che per compile monitoriamo come metrica l'f1 score.

Il prodello prescelto per le previsioni è un LSTM con dropout.
