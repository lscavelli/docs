===================
Portlets principali
===================

Nella pagina Quikstart si è fatto cenno alle :ref:`Portlets <portlet>` come elementi aggregatori di contenuti informativi su una pagina web Newportal. Le portlets possono essere trascinate (in modalità Drag-and-drop) in aree specifiche delle pagine (Dropped aree) in base al modelli di layout adottati.
Le portlet attualmente disponibili sono:

* :ref:`webcontent <webcontent>`;
* :ref:`contentlist <contentlist>`;
* navigationpages;
* navigationcat;
* navigationtag;
* organizations.

Altre portlet sono in fase di realizzazione.

.. _webcontent:

Webcontent portlet
==================

La portlet webcontent consente la visualizzazione di un singolo contenuto informativo nella posizione in cui è posizionata la portlet stessa. L'aspetto del contenuto dipenderà dalla sua struttura dati e dal modello (vista) scelto per la sua visualizzazione.
Lo stesso contenuto informativo, attraverso l'uso di più portlet webcontent, può essere presente in più pagine del sito o più volte nella stessa pagina (in modalità multi istanza), assumendo, in base ai modelli scelti, differenti aspetti.

La scelta del modello può essere effettuata sia nell'editor del contenuto, sia nella finestra di configurazione della portlet.

I modelli possono essere di due tipi: di tipo "lista", quelli utilizzabili nella portlet "contentList" eslusivamente per le righe di una lista; di tipo "base", applicabili al singolo contenuto informativo ed utilizzabili nella portlet "webContent.
I modelli che verranno mostrati nella finestra di configurazione della portlet dipenderanno dalla struttura dati del contenuto selezionato.

Poiché possono essere impostati, per lo stesso contenuto, più modelli, la portlet in fase di visualizzazione del contenuto informativo utilizzerà il seguente ordine di priorità:

1. Modello impostato nella portlet;
2. Modello impostato nell'editor del contenuto;
3. In assenza dei primi due, il primo modello appartenente alla struttura dati del contenuto.

Se il modello non è trovato o non esistono modelli per la struttura del contenuto selezionato, il sistema mostrerà un messaggio di errore.

Selezione manuale del contenuto
--------------------------------
Il contenuto informativo da visualizzare nella portlet, viene selezionato, manualmente, nel pannello di configurazione della portlet. Dopo aver scelto una struttura dati, la finestra mostrerà i contenuti informativi basati sulla struttura selezionata. Cliccare su aggiungi, per selezionate il contenuto.

Selezione dinamica del contenuto
--------------------------------
Se la comunicazione della portlet è attiva (impostabile dalla finestra di configurazione) e nell'URL è presente lo slug di un contenuto informativo valido, questo sarà ricercato e visualizzato nella portlet, indipendentemente dalla presenza di un contenuto impostato manualmente nella portlet. Con tale configurazione una portlet webContent potrebbe visualizzare di default un contenuto informativo e dinamicamente un altro. 
Nella modalità dinamica lo stesso contenuto informativo verrà visualizzato in tutte le portlet webcontent, che avranno la comunicazione impostata su "attiva".

Uno slug di un contenuto informativo può essere presente nell'url nei seguenti modi:

* http://<domain-name>/<page>/<slug-web-content>
* http://<domain-name>?content=<slug-web-content>
* http://<domain-name>/<slug-web-content>

Quest'ultima ipotesi sarà attuabile solo e soltanto se risulterà assegnata al contenuto informativo una pagina di visualizzazione contenente una portlet di tipo webcontent con il parametro "predefinita per questa pagina" impostato su "On".

.. warning::

    La visualizzazione dinamica è consentita solo se i contenuti passati nell'url risultano pubblici (Modalità predefinita) ossia non salvati con l'opzione "gestibili manulamente". Nel caso contrario i contenuti dovranno essere selezionati manualmente attraverso il pannello di configurazione della portlet.

Condivisione del contentuto
---------------------------
Dal pannello di configurazione è possibile abilitare la condivisione del contenuto informativo sui principali social media. Se la condivisione é abilitata, compariranno, a fine testo, sulla destra, le icone dei social disponibili. Cliccando su queste icone si aprirà un popup che consentirà lo sharing del content web sui rispettivi social network. Se al contenuto informativo è stata associata un'immagine, questa comparirà nella finestra di condivisione del social network facebook.

Abilitazione dei commenti
-------------------------
La portlet webcontent consente l'attivazione del modulo per l'invio e la visualizzazione, a piè di pagina, dei commenti. I commenti, in base alla configurazione scelta, possono essere moderati o immediatamente visibili. All'atto della registrazione di un nuovo commento, una notifica di tipo email verrà inviata all'autore del contenuto. I commenti possono essere gestiti nella sezione dei contenuti, dal menu posto a destra in corrispondenza del contenuto interessato.

Abilitazione del conteggio delle visite
---------------------------------------
Dal pannello di configurazione della portlet è possibile attivare il conteggio delle visite al contenuto informativo. Il numero complessivo delle visite può essere visualizzato nella sezione web content del cruscotto di amministrazione, in corrispondenza del contenuto interessato. Il dato sarà considerato dalla portlet contenlist per visualizzare la lista dei contenuti più popolari.

Abilitazione dell'evidenziazione della sintassi
-----------------------------------------------
Spesso i contenuti informativi includono, al proprio interno, dei frammenti di codice. Per facilitare la lettura di questo particolare testo, la portlet "Webcontent" consente l'abilitazione dell'evidenziazione della sintassi - syntax highlighting. Un sistema che supporta una vasta gamma di linguaggi di programmazione, di markup e di scripting ed effettua la colorazione della sintassi in maniera completamente automatica.

.. _contentlist:

Contentlist portlet
===================

La portlet contentlist consente di visualizzare una lista di contenuti formattata in base a determinati modelli scelti nel pannello di configurazione della portlet. Lo stile del contenitore esterno della lista è preimpostato sul modello "listAsset", ma può essere comodamente sostituito con altri modelli, anche custom, presenti nella cartella "view" della portlet "contentlist". In taluni casi si potrebbe aver bisogno di template generici legati espressamente al tema corrente. Questi ultimi sono raccolti nella cartella "partials"  del tema corrente e possono essere selezionati dalla scheda "Altre impostazioni" del pannello di configurazione della portlet.

Attraverso questa portlet la stessa lista può essere utilizzata in più pagine o più volte nella stessa pagina (Multi istanza), assumendo, in base ai modelli scelti, aspetti differenti.

.. warning::

    Nella lista saranno presenti solo i contenuti pubblici ossia quelli che non risultano salvati con l'opzione  "gestibili manulamente".

Filtraggio in base ai Tags e Categorie
--------------------------------------
I contenuti della lista possono essere filtrati in base ai tags e categorie definiti nel sito. Per l'impostazione dei filtri
la portlet utilizzerà il seguente ordine di priorità:

1. Parametri ``tag`` e ``category`` impostati nell'url (Se la comunicazione  della portlet è attiva);
2. Tags e categories del contenuto passato nella URL tramite slug (Se la comunicazione della portletè è attiva);
3. Tags e categories impostati dal pannello di configurazione della portlet (Se la comunicazione è disattiva o i punti precedenti non producono un risultato).

Filtraggio in base alle strutture dati
--------------------------------------
La portlet contentlist consente di filtrare i contenuti informativi in base ad una particolare struttura dati definita nel pannello di configurazione della portlet. Non supporta la modalità dinamica.

Filtraggio in base all'autore del contenuto
-------------------------------------------
Passando semplicemente nell'url parametro "author" con l'identificativo dell'autore, i contenuti informativi saranno filtrati in base all'autore. Questo filtro si aggiungerà agli altri filtri.

Visualizzazione dei contenti più popolari
-----------------------------------------
I contenuti informativi possono essere ordinati anche in base al numero delle visite. Se la direzione è discendente, in testa comparirà il contenuto con il maggior numero di visite, altrimenti il contenuto con il minor numero di visite.

Ordinamento delle voci
----------------------
Oltre che per "visite", i contenuti della lista possono essere ordinati per: - Inserimento; - Titolo; - Data di creazione; - Data di modifica. In abbinamento a questo parametro bisogna impostare anche la direzione (Ascendente, Discendente)

Scrolling a destra e a sinistra
-------------------------------
Un'altra funzionalità importante della portlet è quella di visualizzare il link al contenuto precedente e successivo rispetto allo slug passato nella URL. La comunicazione della portlet dovrà essere attiva e si dovrà impostare il selettore Scrolling al valore desiderato.

Abilitazione dei Feed
---------------------
Attraverso l'uso della portlet contentlist, i contenuti pubblicati sul sito possono essere resi disponibili anche in formato RSS (Really Simple Syndication ). Dal pannello di configurazione sarà necessario abilitare tale funzionalità e dopo aver inserito il Titolo del feed, il numero di elementi da visualizzare e scelto il formato da utilizzzare fra Atom 1.0,  Rss 2.0, la portlet riporterà, in basso a sinistra, una icona che consentirà l'estrapolazione del feed in formato XML.

Il link può essere copiato e incollato in un aggregatore di feed (Reader).
I feed  consentono di notificare la pubblicazione di un nuovo contenuto su Web e permette di aggregare facilmente i contenuti di diversi siti e presentarli sotto altre forme.

I feed rss elaborati rispetteranno fedelmente le impostazioni delle portlet, ed in particolar l'applicazione dei filtri per la selezione dei contenuti.

Nella stessa pagina più portlet contentlist possono avere i feed abilitati.

.. important::

Attenzione: i feed, se abilitati, sono fruibili anche nel famoso formato JSON Feed Version 1.0.

Site Map
--------
Il sistema consente la creazione automatica del file sitemap.xml secondo le specifiche del protocollo sitemap - ver. 0.9 - Il file Raccoglie tutti gli URL delle pagine e dei contenuti delle "portletList" che hanno il sitemap abilitato. L'url delle pagine è di default inserito nel sitemap. Per le portlet "contentList" il sitemap va abilitato dal pannello di configurazione della portlet.