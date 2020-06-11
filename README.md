### Spiegazione Video sul canale Node Red Italia

https://www.youtube.com/watch?v=cNk22oKGPao&t=52s


### About

Questo progetto mira ad automatizzare la chiusura delle tapparelle in base a 3 funzionalità:
1.	Al tramonto 
2.	In base ad un orario definito
3.	Disabilitato
	

### Prerequisiti
Alexa Remote2 su NodeRed già configurato. 

Entità sun.sun (https://www.home-assistant.io/integrations/sun/)

Entità cover configurate. (Nell’esempio ne trovate 7)

*Una variabile input_datetime.chiusura_manuale_tapparelle (Scelta dell'orario in caso di "Scelta Orario")
*Una variabile input_select.tapparelle_chiusura_automatica (deve contenere le 3 opzioni specificate prima)
*Una variabile input_boolean.tapparelle_manuale_temp (una variabile di appoggio)
*Una variabile input_boolean.alexa_blocca_azione (serve per bloccare la partenza del automatismo dicendo “Alexa Blocca Azione”). 
I nodi DND ATTIVO e DND MANUALE sono specifici per il DND di Alexa (Rimuovere se non utilizzati)
*Automazione Orario Manuale Su Tapparelle
Aggiungere il package variabili_TapparelleHANR.yaml alla vostra cartella package per avere le variabili e l’automazione.
*le configurazioni sono incluse nel file yaml.


### Come funziona
Scegliere da Home Assistant tra i 3 tipi. Solo se si è scelto un orario specifico indicare anche l’orario nel campo Chiusura Manuale Tapparelle.
#YAML
Inserire le entità input_select.tapparelle_chiusura_automatica e input_datetime. chiusura_manuale_tapparelle dove preferite ed il gioco è fatto.


## Ricordarsi di creare una routine su Alexa tramite la app Quando senti: “Alexa Blocca azione” porta la input_boolean.alexa_blocca_azione a ON
## Per i meno esperti di GitHub
Andare su find file:

Scaricare il file o copiarsi il codice dentro la cartella package
Creare un nuovo flow su NodeRed. Entrare nel file flow.json su github. Copiare tutto il codice e fare import dentro il flow appena creato.

### New feature
Chiusura automatica delle tapparelle aperte ad un orario da stabile nel timestamp. Attenzione si chiudono solo le tapparelle che sono aperte più del 20% in quanto potrebbe essere che qualcuno le tenga aperte durante la notte per far passare l'aria.