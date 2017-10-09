==========
Quickstart
==========

Questa pagina fornisce una rapida introduzione a Newportal ed esempi introduttivi.
Se non hai ancora installato Newportal, vai alla pagina :ref:`installation`.

Front end with portlets
================

Una ``portlet`` è un componente modulare che aggrega contenuti informativi su una pagina web.
Una sorta di plug-in che lavora lato server e consente la pubblicazione di informazioni
in porzioni di pagina.
Tramite le portlets lo stesso contenuto è utilizzabile in più pagine o più volte nella
stessa pagina (Multi istanza).
Le portlets possono essere trascinate in aree specifiche della pagina in base al
modello di layout adottato. Durante il trascinamento si attiva un indicatore di colore
blue in corrispondenza delle aree di rilascio. All'interno della stessa area sarà
possibile disporre più portlets e ordinarle diversamente. Grazie al supporto
al Drag-and-Drop, le pagine del portale potranno essere riorganizzate rapidamente.

Web Content
================

I contenuti web sono contenuti strutturati che compongono le pagine del portale.
Si basano essenzialmente sulle Strutture (form per l'acquisizione dei dati informativi)
e sui Modelli (Viste di presentazione dei dati). Un tool visuale, basato su Formero,
consente agevolmente di costruire, in base alle proprie esigenze, strutture semplici
e complesse alle quali sarà possibile associare uno o più modelli (dynamic template).
Lato front-end le portlets possono estrarre Web Content che rispondano a determinate
strutture (ex. news / eventi) ed assumere differenti aspetti in base al modello scelto
di visualizzazione.

Dynamic Data List
================
Attraverso i Dynamic Data List è possibile definire un elenco dati dinamico, ovvero
un elenco di contenuti web basato sulla medesima struttura, esportabile nei diversi
formati (excel, csv, xml, txt, etc...). Così come avviene per i Contenuti web, la
creazione dei "Dynamic Data List" richiede l'impostazione di una struttura dati.

Categorization
================

Newportal consente la creazione di più vocabolari per aggregare un numero quasi infinito
di categorie omogenee.  I vocabolari possono essere associati a più servizi del
portale e resi accessibili separatamente attraverso la sezione "Categorizzazione". 
Contestualmente alle categorie è possibile definire e associare i tag, in modo da
rendere i contenuti facilmente ritrovabili e filtrabili anche lato front-end.

Frontend side
----------------

Con l'uso di appositi widgets sarà possibile creare pagine web complete di menu
di navigazione basati su vocabolari di categorie e tags. Gli elementi che aggregano
i contenuti presenti nella pagina consentiranno di filtrare i dati in base ai
valori dei vocabolari definiti in configurazione o in base alla categoria passata
nell'url, se la comunicazione tra portlets è stata abilitata.

Pages, themes and layouts
================

Newportal gestisce sia pagine pubbliche (accessibili a chiunque) che private. 
Le pagine private sono accessibili solo agli utenti membri del sito che possiede
le pagine. Per impostazione predefinita tutte le pagine vengono automaticamente
mostrate nei menu di navigazione. Se si vuole omettere tale visualizzazione, la
pagina dovrà essere creata come nascosta. Le pagine possono essere: - nidificate
ovvero create come sotto-pagine di altre pagine esistenti; - vuote o precompilate,
partendo da dei modelli di pagina predefiniti; - di tipo Portlet, URL o Link interno.
In base al tema e al layout scelto, le pagine possono assumere aspetti differenti.
i layout consentono di specificare come le portlet saranno disposte nelle pagine.
Possono essere creati e resi disponibili per lo stesso sito diversi layout. 
Con alcune piccole modifiche sarà possibile utilizzare themes e templates
fully responsive facilmente reperibili su web

User management
================

Dal pannello di controllo un amministratore può: gestire gli utenti del portale,
raggruppandoli in team di lavoro o inserendoli in organizzazioni gerarchiche; 
assegnare ad utenti e gruppi di utenti i permessi (privilegi di accesso alle
risorse del sistema) o i ruoli (insieme di permessi); accedere a tutti i profili
definiti dal sistema (utente, gruppo, permesso, ruolo, organizzazione).
Se abilitato, il modulo di registrazione per creare i nuovi utenti può essere
liberamente accessibile.
Attraverso la pagina di login gli utenti potranno autenticarsi al portale,
digitando il proprio nome utente (o email) e password, oppure utilizzando alcune
delle opzioni sociali di autenticazione.
Qualsiasi accesso alle risorse protette del sistema effettuato da un utente non
registrato sarà rediretto alla pagina di login.
L'attività degli utenti è registrata. Un utente non amministratore avrà accesso
solo al registro della propria attività. Il sistema consente anche la visualizzazione
delle sessioni attive con possibilità per l'utente amministratore di cancellarle.


.. code-block:: php