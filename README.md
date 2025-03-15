# Entorns de desenvolupament o Ecosistemes 
Repositori destinat a la documentació de preparació d'entorns de desenvolupament o ecosistemes

* Instal·lació Python
* Instal·lació IPyton
* Instal·lació Spark

# Instal·lació Python

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
robert-desktip:src$ virtualenv test-env
```
Això ens ha creat una carpeta ```test-env``` al directori actual. Si mirem el contingut de la carpeta trobem:
```cmd
dir test-env

<DIR>          Lib
               pyvenv.cfg
<DIR>          Scripts

```
```shell

```














