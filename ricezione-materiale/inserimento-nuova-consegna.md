# Inserimento nuova consegna

All'apertura della pagina vengono caricate nel box "Elenco ordini da consegnare" tutte le righe in view\_p7\_ordini\_non\_consegnati con fornitore uguale a quello selezionato.

<figure><img src="../.gitbook/assets/Immagine31 (1).png" alt=""><figcaption></figcaption></figure>

Lo scopo della pagina è ricreare a destra la "versione digitale" del documento di trasporto che si sta registrando.

Va inserito in alto a destra la data e il numero del documento di trasporto ricevuto.

A sinistra è possibile selezionare l'ordine da consegnare o cliccare sul pulsante consegna completa.

In caso di selezione nella parte bassa a sinistra vengono caricate dalla vista view\_p2\_materiali\_non\_consegnati le righe relative all'ordine selezionato.

Per ogni riga d'ordine è possibile cliccare sul pulsante + o sul pulsante consegna parziale. Il pulsante consegna parziale apre un pop-up in cui è possibile inserire la quantità ricevuta( tale quantità non può essere negativa e se è superiore a quella ordinata va evidenziata in rosso.

Quindi le tre modalità per riempire la parte di destra sono:&#x20;

-pulsante consegna completa dell'ordine

-pulsante + consegna completa riga d'ordine

-pulsante consegna parziale riga d'ordine

Tutte queste modalità hanno l'effetto di riempire il box di destra e di disabilitare o nascondere nei box di sinistra ciò che è stato inserito.

&#x20;Il pulsante inserisci consegna ha il seguente effetto.

```mermaid
graph TD
subgraph back
emetti[Inserisci consegna]-->salvo_p8["Salvo i dati
dell'intestazione in p8
e ottengo dal DB
id_consegna"]
salvo_p8-->salvo_p5["Salvo i dati di
ogni riga in P5"]
salvo_p5-->check_1["Se qtà_consegnata > qtà_da_consegnare
salvo il bit
consegna_in_eccesso=1"]
end
salvo_p8-->db[(Database)]
db-->|id_consegna|salvo_p8
salvo_p5---db
```

