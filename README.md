# corsoAi
Corso Ai Strategist - Fano - 2025/2026

# Introduzione al linguaggio SQL per i Database Relazionali

------------------------------------------------------------------------

## 1. Cos'è SQL?

SQL (Structured Query Language) è il linguaggio utilizzato per
comunicare con un database relazionale.

Serve per:

-   leggere dati
-   inserire nuovi dati
-   modificare dati esistenti
-   eliminare dati

I dati in un database relazionale sono organizzati in **tabelle**,
composte da:

-   righe (record)
-   colonne (campi)

------------------------------------------------------------------------

# 2. SELECT -- Leggere i dati

Il comando `SELECT` serve per **leggere e visualizzare i dati** presenti
in una tabella.

## Sintassi base

``` sql
SELECT nome_colonna
FROM nome_tabella;
```

### Esempio

``` sql
SELECT nome
FROM clienti;
```

------------------------------------------------------------------------

## Selezionare tutte le colonne

``` sql
SELECT *
FROM clienti;
```

------------------------------------------------------------------------

## Usare WHERE per filtrare

``` sql
SELECT *
FROM clienti
WHERE città = 'Roma';
```

------------------------------------------------------------------------

# 3. INSERT -- Inserire nuovi dati

``` sql
INSERT INTO nome_tabella (colonna1, colonna2)
VALUES (valore1, valore2);
```

### Esempio

``` sql
INSERT INTO clienti (nome, città)
VALUES ('Mario Rossi', 'Milano');
```

------------------------------------------------------------------------

# 4. UPDATE -- Modificare dati esistenti

``` sql
UPDATE nome_tabella
SET colonna = nuovo_valore
WHERE condizione;
```

### Esempio

``` sql
UPDATE clienti
SET città = 'Torino'
WHERE nome = 'Mario Rossi';
```

⚠️ Senza `WHERE` vengono aggiornati tutti i record.

------------------------------------------------------------------------

# 5. DELETE -- Eliminare dati

``` sql
DELETE FROM nome_tabella
WHERE condizione;
```

### Esempio

``` sql
DELETE FROM clienti
WHERE nome = 'Mario Rossi';
```

⚠️ Senza `WHERE` elimina tutti i record della tabella.

------------------------------------------------------------------------

# 6. Introduzione ai JOIN

Un `JOIN` serve a **unire i dati di due tabelle** in base a un campo
comune.

Esempio di tabelle:

-   clienti (id, nome)
-   ordini (id, id_cliente, importo)

## INNER JOIN (il più comune)

``` sql
SELECT clienti.nome, ordini.importo
FROM clienti
JOIN ordini ON clienti.id = ordini.id_cliente;
```

Mostra il nome del cliente insieme al suo ordine.

Concetto chiave:\
Il JOIN collega le tabelle tramite una relazione tra chiave primaria e
chiave esterna.

------------------------------------------------------------------------

# 7. Introduzione al GROUP BY

Il `GROUP BY` serve per **raggruppare i dati** e usarli con funzioni di
aggregazione come:

-   COUNT() → conta
-   SUM() → somma
-   AVG() → media
-   MAX() → valore massimo
-   MIN() → valore minimo

## Esempio

Conta quanti clienti ci sono per città:

``` sql
SELECT città, COUNT(*) as totale
FROM clienti
GROUP BY città;
```

Il risultato mostra una riga per ogni città con il numero di clienti.


------------------------------------------------------------------------

# Messaggio chiave

SQL è il linguaggio fondamentale per gestire i dati.\
Comprendere SELECT, INSERT, UPDATE, DELETE, JOIN e GROUP BY significa
avere le basi per lavorare con qualsiasi sistema informativo.

