# konkur
The incurable mental illness known as "Italian fixed-term research contract" isn't a good excuse for having to fill out forms in RTF format.

# Cos'è konkur

L'umiliazione di partecipare a un concorso per RTD in Italia è solo inasprita dal disagio di dover compilare documenti di testo scritti in formati dichiarati cerebralmente morti nel 1995. 

Molto meglio un formato pdf customizzabile (la burocrazia non sarebbe la condanna a morte dell'intelletto che tutti conosciamo, se la sua prassi non fosse sottilmente diversa da ateneo ad ateneo). All'ennesima volta in cui ho dovuto compiere la stessa operazione con gli stessi problemi tecnici, mi sono stancato e ho deciso di rifare tutto daccapo _una volta sola_.

# Come si usa konkur

* Se è necessario, si modifica il `.tex` per adattarlo alle specifiche del concorso cui partecipare; alcune parti del documento si devono editare per forza, dato che minuzie burocratiche come il numero di protocollo della pratica, o l'esatta posizione di tale numero nella testatina del documento, la presenza e l'esatta scala della firma vidimata da un druido, il numero di item nella lista delle posizioni precedentemente occupate dal ricercatore, etc... cambiano tutte in modo imprevedibile e richiedono modifiche soggettive. 
* Idealmente, la testatina -generata con `fancyhdr`- contiene codici burocratici, e si modifica cambiando il contenuto delle graffe in
  ```tex
  \rhead{Allegato A}
  ```
  nel file `layout.tex` mentre il corpo del testo contiene le informazioni essenziali comuni a tutte le competizioni (le dichiarazioni riguardanti l'illibatezza penale, i dati anagrafici, e la non-consanguineità con i membri del dipartimento sono litanìe standard).
* Si apre il pdf e si compilano uno ad uno i campi liberi con informazioni anagrafiche e accademiche. Dal primo campo libero ("__ sottoscritt__", dove si dà una specificazione di genere), a tutti gli altri campi si passa, ciclicamente, premendo `TAB`.
* Se si vuole (nei casi in cui si può) inviare la domanda per email, esiste la possibilità di firmarlo con il comando `\sign`, che viene definito in `\layout.tex` come
  ```tex
  \newcommand{\sign}[2][.175]{%
   \begin{flushright} 
   \includegraphics[scale=#1]{#2}
   \end{flushright}%
   }
  ```
  Una specifica del tipo `\sign[.2]{firma.pdf}` in calce al documento apporrà la propria firma. Alternativamente, è chiaramente possibile stampare il pdf, firmarlo, e spedirlo a traino di yak fino alla segreteria dell'università scelta.
* Ovviamente, qualsiasi modifica necessaria è attuabile editando il file `layout.tex` o `rtd{a,b}.tex` allo stesso modo di ogni altro file `.tex`.
