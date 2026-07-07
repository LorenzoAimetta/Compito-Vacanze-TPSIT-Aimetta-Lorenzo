# Compito-Vacanze-TPSIT-Aimetta-Lorenzo
Progetto battaglia navale sviluppato da Aimetta Lorenzo come compito delle vacanze di TPSIT.

Il tema scelto è Battaglia Navale, versione "single player" contro il computer: ovvero il computer piazza le navi e tu devi trovarle tutte prima che scada il tempo.

Griglia: 8x8 caselle
Navi: 8 in totale — 1 da 4 caselle, 2 da 3, 3 da 2 e 2 da 1 (18 caselle occupate su 64)

Posizionamento: casuale a ogni partita, tramite un ciclo che genera riga, colonna e orientamento (orizzontale/verticale) a caso, controllando che la nave non esca dalla griglia e non si sovrapponga a un'altra già piazzata; se il tentativo non va bene, ne genera un altro finché non trova un posto valido

Temporizzazione: conto alla rovescia di 45 secondi, gestito con setInterval, con cambio colore della barra (verde - giallo - rosso) man mano che il tempo si esaurisce

Elementi creati dinamicamente con JavaScript: le 64 celle della griglia vengono generate una a una con createElement e collegate ai relativi eventi di click, il colore di ogni cella viene assegnato via style.backgroundColor, e i contatori (tentativi effettuati, rimanenti, colpite) vengono aggiornati in tempo reale nell'HTML.



Funzionalità facoltative aggiunte:

-Contatore di tentativi effettuati e rimanenti (oltre al limite di 45 mosse)

-Contatore delle caselle "nave" colpite, per sapere quante ne mancano su 18

-Timer visivo che cambia colore (verde → giallo a 25s → rosso a 10s) per dare un senso di urgenza

-Messaggio finale di vittoria/sconfitta con stile diverso

-Pulsante "svela" che mostra tutte le navi rimaste, ma solo dopo aver perso

-Pulsante di reset che rigenera una partita completamente nuova (nuova disposizione navi, timer e contatori azzerati) senza dover ricaricare la pagina



Difficoltà incontrate:

-Far coincidere il posizionamento casuale delle navi senza farle sovrapporre o uscire dalla griglia: risolto con un ciclo che ritenta finché non trova una posizione libera

-Gestire correttamente riga e colonna di ogni cella dentro l'evento di click: usando const dentro il ciclo,così ogni cella "ricorda" le proprie coordinate corrette (altrimenti con let tutte le celle avrebbero puntato all'ultimo indice del ciclo)

-Sincronizzare il colore "logico" della cella (salvato nella matrice) con quello visivo mostrato solo al click, per non svelare le navi in anticipo

-Reset completo dello stato di gioco (timer, colori, contatori, classi CSS) senza lasciare residui della partita precedente
