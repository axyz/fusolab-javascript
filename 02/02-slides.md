Ambiente di Sviluppo
====================
- editor di testo (sublime, notepad++, emacs, vim, etc...)
- browser web (chrome, firefox)
- sandbox online (jsbin, jsfiddle, etc...)


---


Risorse nel Web
===============
- [MDN](https://developer.mozilla.org/it/)
- [MSDN](http://msdn.microsoft.com/it-it/default.aspx)
- [w3school](http://www.w3schools.com/)
- [quirksmode](http://www.quirksmode.org/) : incompatibilità tra browsers
- [ECMAScript](http://www.ecma-international.org/publications/standards/Ecma-262.htm) : specifiche formali del linguaggio
- [W3C DOM](http://www.w3.org/DOM/DOMTR)


---


Hello World!
============


----


versione alert
--------------
index.js:
```javascript
alert('Hello World!');
```

index.html:
```HTML
<script src="index.js" >< /script>
```


----


versione console
----------------
index.js:
```javascript
console.log('Hello World!');
```

index.html:
```HTML
<script src="index.js" >< /script>
```


---


Utilizzo console
================
JavaScript è un linguaggio di scripting che non necessita di precompilazione,
quindi tramite la console possiamo eseguire delle istruzioni sequenzialmente
e vederne il risultato immediatamente.


----


qualche esempio
---------------
i nostri "hello world"
***
```Javascript
3+2
```
***
```javascript
window.location.href = "http://www.google.it"
```
***
```javascript
document.bgColor = "red"
```


----


interazione
-----------
- prompt
- confirm
- window.location.hash
- etc... (lista infinitamente lunga)

----


autocomplete
------------
Le console dei browser moderni come chrome e firefox offrono suggerimenti
per completare le istruzioni che scriviamo in console.
Approfittate di questa caratteristica, in quanto permette di prendere
rapidamente confidenza con il linguaggio, nonchè di esplorare le proprietà
di tutti gli oggetti.


---


Utilizzo Sandbox
================
Serivizi come [JSBin](http://jsbin.com) permettono di creare e condividere
online piccole applicazioni basate su html + js + css senza la necessità
di dover ogni volta creare i file localmente e gestire le importazioni.

> La pigrizia è una virtù!


---


Esercizio
=========
Chiedere in input una stringa e restituirla al contrario tramite `alert`
oppure `console.log`.

suggerimenti:

- `var x = "a"` salva nella variabile x la stringa "a"
- `"stringa".split(separatore)` divide la stringa in una lista di elementi
  (array) in base al separatore indicato
- cercate con l'autocomplete i metodi che si possono applicare ad un array...


----


Esercizio
=========
Chiedere in input un indirizzo email e restituirlo con le chiocciole ed i punti
sostituiti con "[at]" e "[dot]".

Per semplicità dare per certo che verrà dato in input un indirizzo email valido
e che nel dominio della mail ci possa essere un solo punto.

Es. axyzxp@gmail.com -> axyzxp[at]gmail[dot]com

mario.rossi@yahoo.it -> mario.rossi[at]yahoo[dot]it
