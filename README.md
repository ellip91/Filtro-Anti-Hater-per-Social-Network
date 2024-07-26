In questo progetto si va a  costruire un modello in grado di filtrare i commenti degli utenti in base al grado di dannosità del linguaggio.

Gli step che sono stati eseguiti sono i seguenti:  
- Preprocessare il testo eliminando l'insieme di token che non danno contributo significativo a livello semantico  
- Trasformare il corpus testuale in sequenze  
- Costruire un modello di Deep Learning comprendente dei layer ricorrenti per un task di classificazione multilabel  

Il modello ritornerà un vettore contenente un 1 o uno 0 in corrispondenza di ogni label presente nel dataset (toxic, severe_toxic, obscene, threat, insult, identity_hate).  
In questo modo, un commento non dannoso sarà classificato da un vettore di soli 0 [0,0,0,0,0,0]. Al contrario, un commento pericoloso presenterà almeno un 1 tra le 6 labels.
