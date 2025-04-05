#Uni/Insegnamenti/Secondo_Anno/FPW 
# Introduzione ai Database
Un database è una collezione strutturata di dati

Esistono diversi database engine:
- MySQL
- PostgreSQL
- ...

I dati di un database sono acceduti e modificati tramite un linguaggio standard SQL

## Tabelle
I dati di un database sono organizzati in tabelle
...
Ogni tabella è costituita dai dati e la sua struttura

### Creazione delle tabelle
Per creare una tabella abbiamo bisogno di un nome per la tabella e un nome e tipo di dato per ogni colonna

È importante studiare la struttura del database prima dell'inseriemtno di dati

### Non fare
Tabellone

# Progettare un database
## Passo 1: individuare le entità
Un'entità è 
Ogni entità avrà una serie di attributi, tra questi un identificatore univoco

### Le chiavi primarie

Possiamo utilizzare più di un campo come chiave primaria per identificare una riga
Una chiave primaria è una chiave con il numero minimo di campi che mi permette di identificare un'entità

## Passo 2: Identificare le relazioni
### Relazioni uno a uno

### Relazioni uno a molti

### Relazioni molti a molti

### Stabilire il tipo di relazione

### Attributi nelle relazioni

# Esempio il mondo degli esami universitari
- Un esame ha una commissione, composta da un docente del corso (presidente) e due docenti

## Esame - Docente presidente
Uno a molti

## Esame - Docente commissario
Molti a molti

## Esame - Studente
Uno a molti

## Dalle entità-relazioni a tabelle
### Trasformiamo le entità in tabelle

### Trasformiamo le relazioni in tabelle
- Uno a uno: **vincolo di chiave esterna** su una tabella qualunque
- Uno a molti: **vincolo di chiave esterna** sulla tabella che ha cardinalità molti
- Molti a molti: si crea una nuova tabella, rappresentante la relazione, che contiene i riferimenti alle due entità

# Creare e gestire un database
## Accesso a un database
Il database server mantiene una lista di utenti che possono accedere ai database che contiene

Si può accedere a un database in tre modi
- Command line
- GUI (pgAdmin)
- Tramite API (JS)

## Inviare comandi a un database
Si usa SQL
Quattro tipi di comando:
- Data Definition:
- Data Manipulation:
- Query:
- Control:

## CRUD: permessi
- Create
- Read
- Update
- Delete

## SQL: Creazione di un database
```sql
CREATE DATABASE <nome_database>;
```

```sql
CREATE USER '<user>'@'<hostname>' IDENTIFYBY '<password>';
```

Se qualcosa va storto riceviamo un codice di errore

## Utilizzo di un database
```sql
GRANT ALL PRIVILEGES ON <esami>.* TO '<user>'@'<hostname>';
```
Al posto di ALL possiamo specificare quali privilegi

```sql
USE <esami>;
```

## SQL: Tipi di dato
### Testo
- CHAR(n): utilizza sempre tutti i caratteri
- VARCHAR(n): usa AL PIÙ i caratteri specificati

### Numeri
- TINYINT
- SMALLINT
- MEDIUMINT
- INT
- BIGINT
- FLOAT
- DOUBLE or REAL
- BOOL (TINYINT in realtà)
- SERIAL (alias di BIGINT unsigned) che si assicura non ci siano duplicati per le chiavi

### Date e tempo

### Dati binari

## Manipolazione delle tabelle

```sql
CREATE TABLE <nome_tabella> (
	<nome_attributo> <tipo_attributo>,
	...
);
```

```sql
DROP TABLE <nome_tabella>;
```

```sql
SELECT * FROM <nome_tabella>
WHERE FALSE;
```
Questo permette di visualizzare la struttura della tabella

### Definire la chiave primaria
```sql
CREATE TABLE <nome_tabella> (
	<nome_campo> <tipo_campo> NOT NULL PRIMARY KEY,
	...
);
```
Così lo definiamo alla creazione della tabella

```sql
CREATE TABLE <nome_tabella> (
	<nome_campo1> <tipo_campo> NOT NULL,
	<nome_campo2> <tipo_campo> NOT NULL,
	...
	CONSTRAINT PRIMARY KEY(<nome_campo1>, <nome_campo2>)
);
```

```sql
ALTER TABLE <nome_tabella>...
```

### Chiave esterna
```sql
CREATE TABLE <nome_tabella> (
	<nome_campo> SERIAL PRIMARY KEY,
	...
	<nome_campo_n> <tipo_campo_n>,
	FOREIGN KEY <nome_campo_n> REFERENCES <altra_tabella>(<nome_campo_chiave>)
	ON UPDATE CASCADE
	ON DELETE SET NULL
);
```

## Inserimento dei dati
```sql
insert into <nome_tabell>
(...)
values
(...)
```

Keyword `default`

## Ricerca di dati (la vera query)
```sql
select (<attributi>)
from <nome_tabella>
where <clausole>;
```

## Modifica di un dato
```sql
update <tabella>
set <cose da settare>
where <clausole>;
```

## Cancellazione di un dato
```sql
delete
from <tabella>
where <clausole>;
```

## Ordinamento
Possiamo ordinare i risultati di una select secondo un preciso ordine
```sql
select *
from <tabella>
order by <campo1> [<campo2> ...] [desc];
```

## Contare elementi
```sql
select count(*)
from <tabella>
where <clausole>;
```

## Limitare le righe di una query
```sql
select *
from <tabella>
limit <n>;
```
```sql
select *
from <tabella>
limit <start>,<n>;
```

0-based

## Ricerche con pattern
`LIKE`
`_`: un carattere
`%`: zero o più

## Ricerche e relazioni
```sql
select 	<tabella1>.<campo1>,
		<tabella1>.<campo1>,
		<tabella2>.<campo2>,
		...
from <tabella1> join <tabella2>
on <primary_key> = <foreign_key>
where <clausole>;
```

Possiamo fare anche Join con più tabelle

