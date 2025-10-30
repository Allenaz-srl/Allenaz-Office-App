# Etichette per materiale consegnato

<figure><img src="../.gitbook/assets/Immagine25 (2).png" alt=""><figcaption></figcaption></figure>

Per garantire la tracciabilità della produzione e una corretta identificazione dei pezzi alla ricezione i pezzi vengono etichettati con l'etichetta sopra riportata. L'etichetta può essere messa sul contenitore (e quindi ne viene stampata una per ogni riga d'ordine) o direttamente sul componente (e quindi ne vengono stampate più di una per ogni riga d'ordine) a discrezione della produzione.\
L'etichetta ha dimensioni 25mmx54mm, viene stampata da una stampante termica DYMO e contiene il thumbnail per semplificare il riconoscimento, il codice (il più grosso possibile per una semplice lettura) sotto più in piccolo il numero d'ordine e la riga d'ordine(id\_riga\_ordine della tabella p2).\
A destra c'è un QR code che contiene le stesse informazioni che già sono riportate sull'etichetta in questo formato:\
\*#AA01#idrio156892#idcon5687#idcom125347#idord1310#\*

In particolare:\


* \*#AA01 -> inizio fisso
* \#\* -> terminazione fissa
* \# come separatore
* idrio seguito da id\_riga\_ordine di p2
* idcon seguito da id\_consegna p8 (è presente in p5 come rif\_consegna)
* idcom seguito da id\_componente di anagrafica\_componenti (è presente in p2 come rif\_componente)
* idord seguito da id\_ordine di p7  (è presente in p7 come rif\_ordine)

idcom e idord sono in teoria inutili, perchè idrio è già univoco. Sono da usare come validazione del messaggio per verificare la coerenza.
