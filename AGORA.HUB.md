# AGORA.HUB  

`agora.hub`  è uno standard per la condivisione di contenuti **pubblici**. `agora.hub` getta le fondamenta per lo sviluppo di un ecosistema cui tutti possono contribuire, come semplice utente o sviluppatore. 

Grazie a uno standard pubblico e a licenza aperta, tutti possono partecipare al network e nessuno può esserne escluso. Per partecipare, è necessario: 

1. poter pubblicare contenuti online raggiungibili attraverso un indirizzo URL;
2. indicizzare i contenuti attraverso lo standard `agora.hub`.

...

> "`agora.hub `  è così *decentralizzato* che per partecipare non devi nemmeno iscriverti!" 

## Ochei, concretamente, di cosa si tratta?

I social network, che ci piaccia o meno (io non sono contrario) sono diventati un *punto focale* della nostra quotidianità. A prescindere dalle opinioni personali sul ruolo di queste piattaforme, tutti sappiamo che sono un *business* non solo molto redditizio, ma anche strategicamente fondamentale.  Gli utenti sono una fonte inesauribile di informazioni monetizzabili, cedono la proprietà dei contenuti, e @ . Non ho voglia di annoiarvi con questi problemi. Parliamo di come risolverli! 

Vogliamo un social, fatto più o meno così:

<blockquote class="twitter-tweet"><p lang="it" dir="ltr">Poi diciamocelo, non avere più in TL tutto lo spam Qanon (sia contro che a favore) è una cazzo di liberazione.</p>&mdash; agora-hub (@HubAgora) <a href="https://twitter.com/HubAgora/status/1313898247161864194?ref_src=twsrc%5Etfw">October 7, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Questo è un `tweet` proveniente da Twitter. La "card" che vediamo, cioè l'aspetto grafico dei contenuti, è una funzione dei dati che deve mostrare. Il vestito non è importante, i dati invece lo sono.

Un `tweet` è una mappa di questo tipo: 

```clojure
{:username "agora-hub"
 :id "@HubAgora"
 :body "Poi diciamocelo, (...)"
 :date ...
 :likes 2
 (altro)
}
```

Ovviamente tutti i tweet condividono la stessa struttura, possiamo chiamarla uno *standard*. Vogliamo farlo anche noi, ma vogliamo rimanere proprietari dei nostri contenuti. 

`agora.hub` fornisce uno schema simile per salvare i contenuti nel proprio spazio. Non è più necessario un server centralizzato ("`agora.hub` è un ecosistema decentralizzato ...") *se* i partecipanti del network aderiscono a uno standard comune. Siccome è molto semplice basterà fare un esempio. Provate a visitare questo link:

[https://lucapanofsky.github.io/agora_standard_poc/test_api/users/utente/agora/2020/09/26/17.10.00.json][https://lucapanofsky.github.io/agora_standard_poc/test_api/users/utente/agora/2020/09/26/17.10.00.json]

la pagina di destinazione è una mappa `agora.hub` 

```json
{
  "type": "post",
  "body": "Ciao Agora! Questo è il mio primo post. Siamo ancora in fase di test.",
  "response_to": false,
  "crowd": "common"
}
```

ma, ancora più importante è il percorso: 

`https://lucapanofsky.github.io/agora_standard_poc/test_api/users/utente/agora/2020/09/26/17.10.00.json`

che ora spezziamo in due parti: 

1. **origine** `https://lucapanofsky.github.io/agora_standard_poc/test_api/users/utente` 
2. **query** `/agora/2020/09/26/17.10.00.json`

**origine** è la parte di URL a partire dalla quale è possibile ricostruire il network dell'utente! ciò è possibile attraverso le **query**. In questo caso, possiamo tradurre la query come

> "vai al contenuto del 26 settembre 2020, scritto alle 17 e 10"

Molto semplice! A breve (...) pubblicherò la documentazione dello schema. Ovviamente prevede dei percorsi prestabiliti dove salvare gli indici/storia dei contenuti. 

L'ecosistema `agora.hub` prevede applicazioni per visualizzare i contenuti. Un'applicazione per visualizzare i contenuti `agora.hub` è un semplice sito web in grado recuperare il contenuto di queste query al momento necessario e di mostrarlo all'utente. L'applicazione deve essere inizializzata attraverso un link `agora.hub`, perché no il proprio link personale, a partire dal quale vengono scoperti e aggiunti altri utenti attraverso un meccanismo di discovery. In parole povere, si tratta di un passa parola automatizzato : ) 

Allo stesso modo però, sarà possibile caricare liste prestabilite di link, che possono essere vere e proprie redazioni o organizzazioni decentralizzate. Questo è un tema molto importante che tratterò in futuro.

## Ochei, non credo di aver capito 

Se non hai capito, non ti preoccupare! "Un giorno capirete ..." battutine a parte : ) spero di uscire al più presto con una applicazione minimale per visualizzare i contenuti e sono sicuro che sarà tutto più chiaro. Almeno, lo spero.

_______________________________

Nel prossimo post mi occuperò del punto 1:

> "poter pubblicare contenuti online raggiungibili attraverso un indirizzo URL". 

Ho individuato due strade per risolvere questo problema (*come faccio a caricare i contenuti ???*) una è preferibile ma è meno amichevole per un utente poco digitalizzato. La seconda invece, è più complicata ma ha il vantaggio di offrire all'utente una esperienza del tutto analoga a quella tradizionale attraverso `GitHub`. Si perde un po' in decentralizzazione, ma su aspetti poco rilevanti e si guadagna in sicurezza ... 

*continua*