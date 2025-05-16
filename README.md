# Roadmap

<figure><img src=".gitbook/assets/Allenaz_office_app.drawio.png" alt=""><figcaption><p>Roadmap Rev0_1</p></figcaption></figure>

{% file src=".gitbook/assets/Roadmap.drawio.png" %}

Schema dell'inserimento componenti/distinta

```mermaid
graph TD
subgraph possibili_input
CSV
INVENTOR
KICAD
end
subgraph fase_iniziale
f_i1[inserimento nuova distinta]-->n_c1[nuovo componente?]
n_c1-->n_c2[inserimento nuovo componente]
n_c2-->f_i1
f_i1-->m_c1[componente modificato?]
m_c1-->m_c2[gestione modifiche componente]
m_c2-->f_i1

end
subgraph fase_finale
f_f1[caricamento distinta]-->f_f2["distinta processata
da produzione:
make or buy"]
f_f2-->f_f3["caricamento in tabella dei
componenti da ordinare"]
f_f3-->f_f4["caricamento in tabella dei
componenti da
stampare in 3d"]
f_f4-->f_f5["caricamento in tabella dei
componenti da lavorare"]
f_f5-->f_f6["caricamento in tabella dei
componenti da saldare"]
f_f6-->f_f7["caricamento in tabella dei
componenti da saldare
a stagno"]
f_f7-->f_f8["caricamento in tabella dei
componenti da montare"]
f_f8-->f_f9["caricamento in tabella dei
componenti da non ordinare"]
end
f_f3-->P1
f_f4-->P?
f_f5-->P9
f_f6-->P0
f_f7-->P0
f_f8-->P0
f_f9-->P0
  possibili_input--> fase_iniziale
fase_iniziale-->fase_finale

```

Schema della creazione ordini

```mermaid
graph TD
subgraph possibili_input
i1[componente già in P1]-->P1
i2[componente da ordinare non in P1]-->i3[caricamento in P1]-->P1
i2-->i4[Ordine diretto??]
end
subgraph fase_iniziale
f_i1["selezione dei
componenti da ordinare"]-->f_i2[selezione del fornitore]
f_i2-->f_i3["revisione dei dati per
l'ordine dei singoli componenti"]
f_i3-->f_i4["inserimento/revisione di
prezzo"]
f_i4-->f_i5["inserimento/revisione di
data di consegna"]
f_i5-->f_i6["inserimento/revisione di
condizioni di pagamento"]
f_i6-->f_i7["inserimento/revisione di
luogo di destinazione"]
end
subgraph fase_finale
f_f0[generazione dell'anteprima dell'ordine]-->f_f1[emissione dell'ordine]
f_f1-->f_f2["assegnazione del
numero d'ordine da DB"]
f_f2-->f_f3["caricamento dell'intestazione
dell'ordine su DB"]
f_f3-->f_f4["caricamento delle
singole righe d'ordine
su DB"]
f_f4-->f_f5["eliminazione da DB
delle corrispettive righe
dei materiali da ordinare"]
end
f_f3-->P7
f_f4-->P2
f_f5-->dat1[cancellare da P1]
  possibili_input--> fase_iniziale
fase_iniziale-->fase_finale
```

Schema della ricezione ordini

```mermaid
```
