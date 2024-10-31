In questo progetto si va a  costruire un modello in grado di filtrare i commenti degli utenti in base al grado di dannosità del linguaggio.

Gli step che sono stati eseguiti sono i seguenti:  
-Effettuo il preprocessing:
Definisco la funzione preprocess_text. Questa funzione esegue la rimozione di punteggiatura, conversione a minuscolo, tokenizzazione, rimozione delle stopwords e lemmatizzazione.
-Separo le features dalle label: Separo i commenti preprocessati (X) dalle etichette (y)
- Divido il dataset in train e test: Utilizziamo train_test_split per dividere il dataset in dati di training e di test.
- Tokenizzare e creare le sequenze: Inizializzo il tokenizer, lo adatto ai dati di training e converto i testi in sequenze.
- Definisco il vocabolario e la lunghezza mediana per semplificare il modello
- Applico il padding alle sequenze per uniformare la lunghezza.  
- Trasformare il corpus testuale in sequenze  
- Costruire un modello di Deep Learning comprendente dei layer ricorrenti per un task di classificazione multilabel  

Il modello ritornerà un vettore contenente un 1 o uno 0 in corrispondenza di ogni label presente nel dataset (toxic, severe_toxic, obscene, threat, insult, identity_hate).  
In questo modo, un commento non dannoso sarà classificato da un vettore di soli 0 [0,0,0,0,0,0]. Al contrario, un commento pericoloso presenterà almeno un 1 tra le 6 labels.
