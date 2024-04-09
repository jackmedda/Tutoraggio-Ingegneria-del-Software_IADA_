# Software Engineering (SWE) e Qualità del Codice

<!-- New section -->

## Scopo della lezione

- Principi di SWE
  - Qualità del codice
  - Collaborazione
  - Testing
  - Pipelines <!-- è necessario avere dei blocchi strutturati di pipeline preimpostate, e.g., data cleaning -->
  - Scaling & Optimization
- Focus: **Formattazione**

<!-- New section -->

## Qualità del codice

Necessità di ridurre gli errori e standardizzare il formato del codice di un software

Organizzare il codice in maniera consistente, leggibile e rimuovere difetti che compromettano le funzionalità

<!-- .element: class="fragment" -->

<!-- New subsection -->

### Benefici

Leggibilità <!-- spendiamo più tempo a leggere piuttosto che scrivere codice -->

Risoluzione di problemi (bug fixing)

<!-- .element: class="fragment" -->

Collaborazione fra sviluppatori

<!-- .element: class="fragment" -->

<!-- New section -->

## Collaborazione

Necessità di lavorare in contemporanea sullo stesso progetto e ricevere un riscontro

<!-- New subsection -->

### Benefici

Rapidità nello sviluppo

Parallelizzazione dei compiti

<!-- .element: class="fragment" -->

Revisione esterna <!-- e.g. del pair programming -->

<!-- .element: class="fragment" -->

<!-- New section -->

## Testing

Necessità di confermare la correttezza del codice dal punto di vista semantico

<!-- New subsection -->

### Benefici

Riduzione nell'introdurre nuovi problemi

Correttezza delle funzionalità

<!-- .element: class="fragment" -->

Aspettative della clientela

<!-- .element: class="fragment" -->

<!-- New section -->

## Pipelines

Necessità di avere una pipeline di esecuzione ben definita, modulare e riusabile

<!-- New subsection -->

### Benefici

Rilevanza in Machine Learning

Specializzazione dei componenti

<!-- .element: class="fragment" -->

Riutilizzo di componenti indipendenti

<!-- .element: class="fragment" -->

<!-- New section -->

## Scaling & Optimization

Necessità di sviluppare software che fornisca buone performance

Tecniche di scalabilità del software su larga scala e ottimizzazione del codice per singole attività

<!-- .element: class="fragment" -->

<!-- New subsection -->

### Benefici

Tempi ridotti di latenza

Riduzione dei costi

<!-- .element: class="fragment" -->

Migliore soddisfazione utente

<!-- .element: class="fragment" -->

<!-- New section -->

## Qualità del codice nel dettaglio

Quando si parla di qualità del codice bisogna considerare

Convenzioni stilistiche di formattazione

<!-- .element: class="fragment" -->

Difetti o sviste associati a una scrittura imprecisa

<!-- .element: class="fragment" -->

Inesattezze logiche

<!-- .element: class="fragment" -->

<!-- New subsection -->

### Linters

*Lint* sono i filaccetti di tessuto che fuoriscono dai vestiti.

I linter rilevano i difetti (i filaccetti) del codice per correggerli (o consigliarci di correggerli)

<!-- New subsection -->

### Tipi di Linters

La maggior parte dei linters si possono suddivider in **logici** e **stilistici**.

Quelli logici rilevano piccoli errori o risultati non previsti.

Quelli stilistici rilevano il codice non formattato secondo convenzioni specifiche.

<!-- New subsection -->

### Esempi di Linters

- [Pylint](https://www.pylint.org/) (logico e stilistico)
- [PyFlakes](https://github.com/PyCQA/pyflakes) (logico)
- [pycodestyle](https://github.com/PyCQA/pycodestyle) (stilistico)
- [Flake8](https://flake8.pycqa.org/) (unione di linter logici e stilistici)
- [Pylama](https://github.com/klen/pylama) (unione di linter logici e stilistici)
- ...

<!-- New subsection -->

### Altri tipi di Linters

Esistono altri tool per il supporto allo sviluppo di software di qualità.

- [mccabe](https://github.com/PyCQA/mccabe): controlla la complessità ciclomatica (McCabe, 1976) del software
- [Black](https://github.com/psf/black): formattatore automatico del codice supportato dalla Python Software Foundation (PSF)
- [pre-commit](https://pre-commit.com/): script per eseguire linters prima di un comando `git commit`

<!-- New section -->

## Convenzioni di formattazione: PEP8

[PEP8](https://peps.python.org/pep-0008) (Python Enhancement Proposal) rappresenta la guida stilistica di Python per
eccellenza che viene aggiornata continuamente con nuove convenzioni o quando precedenti convenzioni diventano obsolete.
[PEP257](https://peps.python.org/pep-0257/) si focalizza sulle docstrings

<!-- New subsection -->

La guida può essere suddivisa in 5 macroaree:
- Disposizione del codice
- Gestione dello spazio vuoto
- Commenti
- Convenzioni di denominazione
- Raccomandazioni di programmazione

<!-- New subsection -->

### PEP8: Disposizione del codice

Descrive le convenzioni in merito a come il codice appare a prima vista. Vengono trattati dettagli come 
l'indentazione (proprietà fondamentale in Python), le andate a capo e l'importazione di librerie.

<!-- New subsection -->

#### Indentazioni

<div class="cols">

```python
foo = long_function_name(var_one, var_two,
    var_three, var_four)

def long_function_name(
    var_one, var_two, var_three,
    var_four):
    print(var_one)
```

```python
foo = long_function_name(var_one, var_two,
                         var_three, var_four)

def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one)
```

</div>

<div class="cols">

❌ Wrong

✅ Correct

</div>

<!-- New subsection -->

Hanging Indents

<div class="cols">

```python
foo = long_function_name(
  var_one, var_two,
  var_three, var_four)
```

```python
foo = long_function_name(
    var_one, var_two,
    var_three, var_four)
```

</div>

<div class="cols">

✅ Correct (optional)

✅ Correct

</div>
