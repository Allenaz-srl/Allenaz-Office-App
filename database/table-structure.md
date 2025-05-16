# Table structure



```mermaid
erDiagram
anagrafica_componenti||--||anagrafica_componenti_settore_merceologico
    anagrafica_componenti{
        big_int id_componente PK
        string codice UK
        text descrizione
int rif_settore_merceologico FK

    }
    anagrafica_componenti_settore_merceologico{
        int id_settore_merceologico PK
        string nome UK
        bit attivo
    }

    agenda{
        big_int id_azienda PK
        string ragione_sociale 
        string p_iva UK
        big_int_not_null rif_sede_legale FK 
    }
agenda_sedi{
big_int id_sede PK
big_int rif_azienda FK
        string_null nome_sede
        string_null presso
        string_not_null indirizzo
string numero_civico
string provincia
string stato
}
agenda_banche{
       
    }
agenda_esenzione_iva{
        
    }
agenda_persona_di_riferimento{
big_int id_persona_di_riferimento PK
big_int rif_azienda FK
        string nome
        string cognome
string email UK
string ruolo
string cellulare UK
string_null note

}
    commesse{
       
    }
bom0_elenco_distinte{
       
    }
bom1_dettagli distinte{
        
    }
bom10_elenco_distinte_processate{
        
    }

bom11_dettagli distinte_processate{
        
    }

p0_materiali_non_ordinati{
       
    }

p1_materiali_da_ordinare{
        big_int rif_componente FK
        big_int rif_lotto_produzione PK, FK
big_int rif_distinta PK, FK
string elemento PK
int quantita
int rif_attributo FK
text note
bit ordinati
string colore
int rif_attributo_ut FK
string quantita_unita
float quantita_materia_prima
big_int rif_fornitore1 FK
big_int rif_fornitore2 FK
big_int rif_fornitore3 FK
date data_di_consegna
int quantita_extra
int quantita_a_magazzino
bit includi
big_int rif_ordine_ricambi
    }

    p2_materiali_ordinati{
big_int id_materiale_ordinato PK
        big_int rif_componente FK
        big_int rif_ordine FK
big_int rif_consegna FK
float quantita_ordinata
text codice_fornitore
text descrizione_fornitore
money prezzo_unitario
string unita_misura
bit a_magazzino
float quantita_consegnata_in_eccesso
date prevista_consegna
    }

p3_allocazione_materiali_ordinati{
big_int rif_materiale_ordinato PK, FK
big_int rif_lotto_produzione PK, FK
big_int rif_distinta PK, FK
int quantita_ordinata
    }

p4_attributo_produzione{
      int id_attributo_produzione PK
      varchar(100) attributo_produzione
bit attivo
    }

p5_attributo_ufficio_tecnico{
      int id_attributo_ufficio_tecnico PK
      varchar(100) attributo_ufficio_tecnico
bit attivo
    }

    p7_ordini_di_acquisto{
        big_int id_ordine PK
        date data_ordine
date data_prevista_consegna
big_int rif_fornitore FK
big_int rif_persona_fornitore FK
big_int rif_sede_destinazione FK
string condizioni_di_pagamento_tramite
int condizioni_di_pagamento_scadenza
string condizioni_di_pagamento_termine_scadenza
string trasporto_a_carico_di
string corriere
money costo_trasporto
money prezzo_totale
text note
int rif_emesso_da FK
int rif_approvato_da FK
int rif_template_ordine FK
bit annullato
    }
p8_consegne{
        big_int id_consegne PK
        date data_consegna
big_int rif_fattura FK
string numero_ddt
    }
    p9_materiali_per_lavorazioni_interne{
       
    }

    p12_materiali_a_magazzino{
        
    }


utenti{
        int id_utente PK
        string nome
        string cognome
string user UK
string email UK
    }
```
