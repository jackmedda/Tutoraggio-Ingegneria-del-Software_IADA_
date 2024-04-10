# Software Engineering (SWE) e Qualità del Codice

<!-- New section -->

## Scopo della lezione

- Principi di SWE
  - Qualità del codice
  - Collaborazione
  - Testing
  - Pipelines <!-- è necessario avere dei blocchi strutturati di pipeline preimpostate, e.g., data cleaning -->
  - Scaling & Optimization
- Focus: **Qualità del codice**

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

Convenzioni stilistiche di formattazione

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

<!-- .element: class="fragment" data-fragment-index="1" -->

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

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

<!-- .element: class="fragment" data-fragment-index="1" -->

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

If statements

<div class="cols">

```python
if (this_is_one_thing and
    that_is_another_thing):
    do_something()
```

```python
if (this_is_one_thing and
    that_is_another_thing):
    # Comment
    do_something()
```

```python
if (this_is_one_thing
        and that_is_another_thing):
    do_something()
```

</div>

<div class="cols">

✅ Correct

✅ Correct

✅ Correct

</div>

<!-- New subsection -->

Opening and closing brackets/parenthesis

<div class="cols">

```python
my_list = [
    1, 2, 3,
    4, 5, 6,
    ]
result = some_function(
    'a', 'b', 'c',
    'd', 'e', 'f',
    )
```

```python
my_list = [
1, 2, 3,
4, 5, 6,
]
result = some_function(
'a', 'b', 'c',
'd', 'e', 'f',
)
```

```python
my_list = [
    1, 2, 3,
    4, 5, 6,
]
result = some_function(
    'a', 'b', 'c',
    'd', 'e', 'f',
)
```

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="1" -->

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

#### Tabulazione o Spazi?

✅ Gli spazi sono preferiti

❌ Non mischiare tabulazioni e spazi

<!-- .element: class="fragment" -->

<!-- New subsection -->

#### Lunghezza righe

La Python standard library impone un limite conservativo di 79 caratteri

Per i commenti e le docstring questo limite è ridotto a 72 caratteri

```python
ipotenusa_al_quadrato = (primo_cateto * primo_cateto
                         + secondo_cateto * secondo_cateto)
```

<!-- .element: class="fragment" data-fragment-index="1" -->

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

```python
with open('/path/to/some/file/you/want/to/read') as file_1, \
     open('/path/to/some/file/being/written', 'w') as file_2:
    file_2.write(file_1.read())
```

<!-- .element: class="fragment" data-fragment-index="1" -->

⚠️ Accettabile in certi contesti

<!-- .element: class="fragment" data-fragment-index="1" -->

<!-- New subsection -->

#### Andata a capo con operatori binari

<div class="cols">

```python
income = (gross_wages
          + taxable_interest
          + (dividends - qualified_dividends)
          - ira_deduction
          - student_loan_interest)
```

```python
income = (gross_wages +
          taxable_interest +
          (dividends - qualified_dividends) -
          ira_deduction -
          student_loan_interest)
```

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

#### Righe vuote

<div class="cols">

```python
def foo():
    ...


def bar():
    ...


class Obj:
    ...
```

```python
class Obj:

    def alice(self):
        ...
    
    def bob(self):
        ...
```

```python
def func():
    # processazione dati
    data = carica_dati()
    data = processa_dati(data)

    # esecuzione training
    result = training(data)
```

</div>

<!-- New subsection -->

#### Import

Sempre all'inizio del file dopo commenti e docstrings

Dovrebbero seguire questo ordine:

<!-- .element: class="fragment" data-fragment-index="1" -->

1. standard library
2. terze parti
3. libreria/applicazione locale

<!-- .element: class="fragment" data-fragment-index="1" -->

<!-- New subsection -->

<div class="cols">

```python
import os
import sys
```

```python
import sys, os
```

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

<div class="cols">

```python
from subprocess import Popen, PIPE
```

```python
from subprocess import (
    Popen,
    PIPE
)
```

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

### PEP8: Apici e Stringhe (String Quotes)

Non ci sono raccomandazioni specifiche, ma si consiglia di essere consistenti nell'usare singoli apici o doppi apici

In caso di stringhe dentro stringhe evitare i backslash se possibile

<div class="cols">

```python
"\"ciao\""
```

```python
"'ciao'"
'"ciao"'
```

</div>

<div class="cols">

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="1" -->

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

### PEP8: Spazi vuoti nelle espressioni e statements

<!-- New subsection -->

#### Spazi fastidiosi

Dentro le parentesi tonde (parentheses), quadre (brackets), graffe (braces)

<div class="cols">

```python
spam(ham[1], {eggs: 2})
```

```python
spam( ham[ 1 ], { eggs: 2 } )
```

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

Tra una virgola e una parentesi

<div class="cols">

```python
foo = (0,)
```

```python
bar = (0, )
```

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

Prima di una virgola (comma), di un punto e virgola (semicolon) o di due punti (colon) 

<div class="cols">

```python
if x == 4: print(x, y); x, y = y, x
```

```python
if x == 4 : print(x , y) ; x , y = y , x
```

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

Quando i due punti sono usati come operatore binario nello slice di una sequenza si applicano convenzioni diverse

<div class="cols">

```python
ham[1:9], ham[1:9:3], ham[:9:3], ham[1::3], ham[1:9:]
ham[lower:upper], ham[lower:upper:], ham[lower::step]
ham[lower+offset : upper+offset]
ham[: upper_fn(x) : step_fn(x)], ham[:: step_fn(x)]
ham[lower + offset : upper + offset]
```

```python
ham[lower + offset:upper + offset]
ham[1: 9], ham[1 :9], ham[1:9 :3]
ham[lower : : step]
ham[ : upper]
```

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

Il PEP8 specifica molti altri casi

Se interessati, tutti i casi possono essere consultati nella pagina dedicata

È comunque doveroso analizzare alcune raccomandazioni aggiuntive

<!-- .element: class="fragment" -->

<!-- New subsection -->

#### Altre raccomandazioni

Aggiungere sempre (*quasi sempre*) uno spazio intorno agli operatori binari di assegnamento (`=`, `+=`, `-=`, ecc.),
comparazione (`==`, `<=`, `not in`, `is`, ecc.), booleani (`not`, `and`, `or`).

<div class="cols">

```python
def complex(real, imag=0.0):
    return magic(r=real, i=imag)

def munge(sep: AnyStr = None): ...
def munge(input: AnyStr, limit=1000): ...

x = 1
long_variable = 3
```

```python
def complex(real, imag = 0.0):
    return magic(r = real, i = imag)

def munge(input: AnyStr=None): ...
def munge(input: AnyStr, limit = 1000): ...

x             = 1
long_variable = 3
```

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

Statement multipli sulla stessa linea sono da evitare

<div class="cols">

```python
if foo == 'blah':
    do_blah_thing()
do_one()
do_two()
do_three()
```

```python
if foo == 'blah': do_blah_thing()
do_one(); do_two(); do_three()

try: something()
finally: cleanup()
```

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="1" -->

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<!-- New subsection -->

### PEP8: Convenzioni di denominazione

Non usare mai la 'l' (elle minuscola), 'O' (o maiuscola), 'I' (i maiuscola) come nome di variabile

I nomi delle classi seguono la convenzione CamelCase, es. `NomeDiClasseInPython`

<!-- .element: class="fragment" -->

Per le variabili e le funzioni si usano nomi in minuscolo con l'underscore (_) come separatore, es. `nome_di_funzione`

<!-- .element: class="fragment" -->

Per le costanti si usano nomi in maiuscolo con l'underscore come separatore, es. `NOME_DI_COSTANTE`

<!-- .element: class="fragment" -->

<!-- New subsection -->

Le classi possono avere metodi per le istanze e metodi per la classe

I metodi delle istanze hanno sempre `self` come primo argomento

<!-- .element: class="fragment" -->

I metodi della classe hanno sempre `class` come primo argomento

<!-- .element: class="fragment" -->

<!-- New subsection -->

Evitare di sovrascrivere nomi appartenenti al linguaggio

Nomi che vengono tipicamente sovrascritti sono `sum`, `lambda`, `input`, `class`, `id`, `vars`, `list`, `set`

<!-- .element: class="fragment" -->

La convenzione suggerisce di trovare dei sinonimi o aggiungere un underscore alla fine, es. `input_`

<!-- .element: class="fragment" -->

<!-- New subsection -->

### PEP8: Raccomandazioni di Programmazione

Singleton come `None` vanno comparati usando `is` o `is not`

`if x` è diverso dallo scrivere `if x is not None` perché `x` potrebbe essere `False` in un certo contesto

<!-- .element: class="fragment" data-fragment-index="1" -->

<div class="cols">

```python
if foo is not None:
```

<!-- .element: class="fragment" data-fragment-index="2" -->

```python
if not foo is None:
```

<!-- .element: class="fragment" data-fragment-index="2" -->

</div>

<div class="cols">

✅ Correct

<!-- .element: class="fragment" data-fragment-index="2" -->

❌ Wrong

<!-- .element: class="fragment" data-fragment-index="2" -->

</div>

<!-- New subsection -->

Per assegnare una funzione a una variabile usare sempre lo statement `def`

<div class="cols">

```python
def f(x): return 2*x
```

```python
f = lambda x: 2*x
```

</div>

<div class="cols">

✅ Correct

❌ Wrong

</div>

<!-- New subsection -->

Evitare di usare una `except` vuota perché può catturare le eccezioni `SystemExit` e `KeyboardInterrupt`

Ereditare da `Exception` piuttosto che da `BaseException` per lo stesso motivo

<!-- .element: class="fragment" -->

<!-- New subsection -->

Per controllare l'inizio o la fine delle stringhe evita l'indicizzazione

<div class="cols">

```python
if foo.startswith('bar'):
```

```python
if foo[:3] == 'bar':
```

</div>

<div class="cols">

✅ Correct

❌ Wrong

</div>

<!-- New subsection -->

Non comparare manualmente i tipi degli oggetti

<div class="cols">

```python
if isinstance(obj, int):
```

```python
if type(obj) is type(1):
```

</div>

<div class="cols">

✅ Correct

❌ Wrong

</div>

<!-- New subsection -->

Le sequence come stringhe, tuple e liste possono essere controllate in maniera diretta in una condizione

<div class="cols">

```python
if not seq:
if seq:
```

```python
if len(seq):
if not len(seq):
```

</div>

<div class="cols">

✅ Correct

❌ Wrong

</div>

<!-- New subsection -->

Le sequence vuote come stringhe, tuple e liste possono essere controllate in maniera diretta in una condizione

<div class="cols">

```python
if not seq:
if seq:
```

```python
if len(seq):
if not len(seq):
```

</div>

<div class="cols">

✅ Correct

❌ Wrong

</div>

<!-- New subsection -->

Non comparare i valori booleani con operatori

<div class="cols">

```python
if greeting:
```

```python
if greeting == True:

if greeting is True:
```

</div>

<div class="cols">

✅ Correct

❌ Wrong

</div>
