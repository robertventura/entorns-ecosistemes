# Entorns de desenvolupament o Ecosistemes 
Repositori destinat a la documentació de preparació d'entorns de desenvolupament o ecosistemes

* [Instal·lació Python](#installacio-python)
* [Instal·lació IPyton i Jupyter](#installacio-ipython-i-jupyter)
* [Instal·lació Spark](#installacio-spark)

## Instal·lació Python

En aquest apartat mostrarem la instalació de Python.
* Python és un llengutge d'alt nivell.
* És un llenguatge interpretat i no compilat.
* És un llenguatge de tipus dinàmic i no formatament tipat (no cal definit el tius de dades que agafarà una variable a la seva declaració).
* És un llenguatge que pos enfasi a la seva llegibilitat. Es va crear perquè fós un llenguatge fàcil de llegir i entendre.
* És un llengautge molt popular que s'utilitza en molts àmbits.

### Python REPL (Read-Eval-Print Loop)
És un entorn interactiu que permet executar codi Python directament i obtenir resultats imediatament.

Normlament REPL de Pyton s'identifica pel prompt ">>>" on es poden introduir comandes.
Podem accedir a REPL executant la comanda "python" en un terminal.

```shell
$ python

Python 3.10.2 (tags/v3.10.2:a58ebcc, Jan 17 2022, 14:12:15) [MSC v.1929 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>

>>>1+1
2
```

### Descàrrega
Podem descarregar Python des de la web oficial [https://www.pyton.org](www.python.org).
A l'apartat de descàrregues podeu trobar les diferents versions de Python per cada Sistema Operatiu [https://www.python.org/downloads/](https://www.python.org/downloads/)
* [https://www.python.org/downloads/windows/](Windows)
* [https://www.python.org/downloads/source/](Linux/UNIX)
* [https://www.python.org/downloads/macos/](MacOS)

### Python Environments (Virtualenv)
[https://virtualenv.pypa.io](virtualenv) és una eina per aïllar entorns de Python.

Per defecte, Python instal·la tots els paquets dins d'un directori global de paquets. ````<directory instal·lació Python>PythonXX\Lib\site-packages```

Aquest tipus de solució és molt simple ja que tots els programes/projectes que realitzem utilitzaran aquests directori per anar a buscar les diferents llibreries que tenim instal·lades.  Això pot semblar una bona ide perquè d'aquesta manera només cal tenir un sol lloc a on s'intal·len els paquets per tots els meus aplicatius i aquests reutilitzen els paquets, però tot això pot presentar molts problemes quan tneim diferents projectes a on a cada projecte tenim necessitats de paquets i versions diferents dels mateixos paquets per temes de compatibilitat.
És aquí a on entren els entorns de Pyton o els **Virtualenv**. Això permet crear entorns de Python aïllats per cada projecte. D'aquesta manera cada projecte pot tenir els seus propis paquets.

Per la instal·lació de Virtualenv cal només executar le següent comanda:
```shell
$ pip install virtualenv
```

```pip``` és un programa de Pyton per instal·lar paquets.

**Creació entorna aïllat**
Per la creació d'un entorn aïllat cal seguir els següents passos:
```shell
$ virtualenv test-env
```
Això ens ha creat una carpeta ```test-env``` al directori actual. Si mirem el contingut de la carpeta trobem:
```shell
$ cd test-env
$ ls

bin
include
lib
```

Per activar l'entorn virtual cal executar l'script d'activació.
Un cop fet això apareixerar al començament del prompt 'test-env' tancat entre parèntesis. Això siginfica que l'entorn virtual s'ha activat.
```shell
$. bin/activate

(test-env)$
```
Windows
```cmd
C:\Users\robert\test-env Scripts\activate.bat

(test-env) C:\Users\robert\test-env>
```

Si volem tornar a l'entorn virtual
```shell
$ virtualenv test-env

(test-env)$
```
Windows
```cmd
virtualenv C:\Users\robert\test-env

(test-env) C:\Users\robert\test-env>
```

## Instal·lació IPython

### Què és IPython
Podriem dir que IPython és una versió millorada de Pyton REPL.
Una de les millores és que disposa d'una memòria caché d'entrada i sortida perquè pugueu fer referència fàcilment a les entrades o sortides anteriors.
IPython també té eines de programació parel·la que poden ajudar a processar grans blocs de dades a través de multiples *cores* de la CPU


### Instal·lació

Prepararem un entorn virtual anomenat ```ipython-env```

```shell
$ virtualenv ipython-env
$ cd ipython-env
$. bin/activate
```
Ara instal·lem IPython mitjançant pip

```shell
(ipython-env)$  pip install ipython

```

### Interacció amb el prompt

```shell
(test-env) $ ipython
Python 3.10.2 (tags/v3.10.2:a58ebcc, Jan 17 2022, 14:12:15) [MSC v.1929 64 bit (AMD64)]
Type 'copyright', 'credits' or 'license' for more information
IPython 8.34.0 -- An enhanced Interactive Python. Type '?' for help.

In [1]: var1 = 1

In [2]:
```
Ara hem declarat la variable ```var1``` amb el valor 1

Podem fer referència a la variable mitjançant el nom de la variable
```ipython
In [2]: var2
Out[2]: 1
```
També podem fer refència a la línia d'entrada de codi [1]
```shell
In [3]: In[1]
Out[3]: 'var1 = 1'
```
Això com fem referència a les línies d'entrada també podem fer referència a les de sortida
```shell
In [4]: Out[2]
Out[4]: 1
```
Això ho podem utilitzar per noves entrades
```shell
In [5]: Out[2] * 2
Out[5]: 2
```

### Ajuda IPython
Per accedir a l'ajuda només cal utilitzar el caràcter ```?```

```shell
In [1]: ?
IPython -- An enhanced Interactive Python
=========================================

IPython offers a fully compatible replacement for the standard Python
interpreter, with convenient shell features, special commands, command
history mechanism and output results caching.

At your system command line, type 'ipython -h' to see the command line
options available. This document only describes interactive features.

GETTING HELP
------------

Within IPython you have various way to access help:

  ?         -> Introduction and overview of IPython's features (this screen).
  object?   -> Details about 'object'.
  object??  -> More detailed, verbose information about 'object'.
  %quickref -> Quick reference of all IPython specific syntax and magics.
  help      -> Access Python's own help system.

If you are in terminal IPython you can quit this screen by pressing `q`.
```

Si necessites ajuda amb alguna funció pot utiltizar `?<nom_funcio>. Això és semblant al man de Linux
```shell
In [1]: ?map

Init signature: map(self, /, *args, **kwargs)
Docstring:
map(func, *iterables) --> map object

Make an iterator that computes the function using arguments from
each of the iterables.  Stops when the shortest iterable is exhausted.
Type:           type
Subclasses:
```

#### Debug

IPython proporciona una commanda de debugger
```shell
In [1]: x=0

In [2]: 1 / X
In [3]: %debug
> <ipython-input-10-d03992758f9d>(1)<module>()
----> 1 1 / x

ipdb>
```

Dins del Debugger 
```shell
ipdb>h

Documented commands (type help <topic>):
========================================
EOF    commands   enable      ll        pp       s                until
a      condition  exceptions  longlist  psource  skip_hidden      up
alias  cont       exit        n         q        skip_predicates  w
args   context    h           next      quit     source           whatis
b      continue   help        p         r        step             where
break  d          ignore      pdef      restart  tbreak
bt     debug      j           pdoc      return   u
c      disable    jump        pfile     retval   unalias
cl     display    l           pinfo     run      undisplay
clear  down       list        pinfo2    rv       unt
```

```w```: Serveix per saber a on estem.
```p```: Mostra per pantalla el que val una variable
```q```: Per sortir del debugger

```shell
ipdb> w
    [... skipping 1 hidden frame(s)]

> <ipython-input-10-d03992758f9d>(1)<module>()
----> 1 1 / x

ipdb> p x
0
ipdb>
```


Amb la comanda ```%pdb``` actives al debugger i et saltarà al debugger quan hi hagi una excepció.

```shell
In [1] %pdb
automatic pdb calling has been turned ON

In [2]: 1/x
---------------------------------------------------------------------------
ZeroDivisionError                         Traceback (most recent call last)
Cell In[2], line 1
----> 1 1/x

ZeroDivisionError: division by zero
> <ipython-input-14-98f9819de3e3>(1)<module>()
----> 1 1/x

ipdb>
```

## Jupyter Notebook

Jupyter permet crear, guardar, carregar i editar sessions de programació mitjançant IPython

És similar a EPL, però pots torna enderrere en qualsevol moment ediar el tall de codi i tornar-lo a executar.

Tot aquesta sessió es pot guardar i compartir-la sense amagar la feina feta ni les sortides que s'han porduït. Això és molt útil per repetir processos que una altra persona ha fet i compartir codi i feina entre companys.

### Instal·lació

Dins de l'entorn aïllat ipython-env instal·larem Jupyter

```shell
(ipython-env)$  pip install jupyter
```

Un cop instal·lat si executem la comanda ```jupyter````ens apareixerà um missatge d'ajuda
```shell
(ipython-env)$ jupyter

usage: jupyter [-h] [--version] [--config-dir] [--data-dir] [--runtime-dir] [--paths] [--json] [--debug]
               [subcommand]

Jupyter: Interactive Computing

positional arguments:
  subcommand     the subcommand to launch

options:
  -h, --help     show this help message and exit
  --version      show the versions of core jupyter packages and exit
  --config-dir   show Jupyter config dir
  --data-dir     show Jupyter data dir
  --runtime-dir  show Jupyter runtime dir
  --paths        show all Jupyter paths. Add --json for machine-readable format.
  --json         output paths as machine-readable json
  --debug        output debug information about paths
```

Per utlitzar el notebooks hem de passar-li el paràmetre notebook
```shell
(ipython-env)$  jupyter notebook
```
Jupyter és un servidor que permet crear sessions. Per crear-ne una només cal anar a File>New>Notebook

![image](https://github.com/user-attachments/assets/b3e585f4-ea0f-486c-aafc-efe0fed2112c)

Un cop creem aquest Notebook tenim una sessió IPython per poder executar codi Python. 

![image](https://github.com/user-attachments/assets/7d7c4f46-d239-44bc-890b-8caf913da63c)


L'avantatge d'utilitzat Notebooks és que poden intercal·lar codi amb cel·les de documentació mitjançant el llenguatge Markdown.

![image](https://github.com/user-attachments/assets/3c4a09ea-10cc-478a-9cd2-3504c4e1dc0d)

D'aquesta manera podem tenir sessions de programació documentades i com hem dit abans reutilizar-les o compartir-les amb altres companys d'una manera fàcil.

El fitxer del Notebook queda emmagatzemat amb extensió **```.ipynb```** Si obres aquest fitxer veuràs que és un fitxer json.


```sessio1.ipynb```

```json
{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "09c633ed-33f1-4d06-aa70-cda2b8d09d4d",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "2"
      ]
     },
     "execution_count": 1,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "1+1"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "bb5f7a89-dbdb-49a4-bc9e-2ead82001358",
   "metadata": {},
   "source": [
    "# Titol del meu Notebook"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "4a234060-f587-40e1-bf7c-9a980926e130",
   "metadata": {},
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.10.2"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
```

















