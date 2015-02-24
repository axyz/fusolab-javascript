ANGULAR.JS PARTE 2
==================



----


Direttive
---------
Le direttive permettono di creare nuovi tag, attributi o classi con
comportamenti definibili da noi.
```
<side-bar>
  <search-box></search-box>
  <main-menu></main-menu>
  <social></social>
</side-bar>
```


----


Creare direttive
----------------
```javascript
app.directive('myTag', ['dep1', 'dep2', function(dep1, dep2) {
  return {
    type: 'E',  // A, E, C
    scope: {
      attr: '='  // =, =name, &, &name, @, @name
    },
    link: fucntion (scope, el, attr) {
      ...
    },
    template: "..."  // o templateUrl
  };
};
```

html:
```
<my-tag attr="foo"></my-tag>
```


----


Esempio
-------
```javascript
app.directive('red', function () {
  return {
    scope: {
      text: '@'
    },
    template: '<span style="color:red">{{text}}</span>'
  };
});
<red text="ciao"></red>
```

```javascript
app.controller('MainCtrl', function($scope) {
  $scope.foo = 'bar';
});
app.directive('red', function () {
  return {
    scope: {
      text: '='
    },
    template: '<span style="color:red">{{text}}</span>'
  };
});
<red text="foo"></red>
```


----


ng-transclude
-------------
Per creare elementi che possono contenere sottoelementi arbitrari si può
utilizzare l'attributo ng-transclude.

```javascript
app.directive('red', function () {
  return {
    transclude: true,
    template: '<span ng-transclude style="color:red"></span>'
  };
});
<red>ciao</red>
```


----


link
----
La funzione link viene eseguita quando la direttiva è stata inserità
nell'applicazione ed è il luogo ideale dove definire comportamenti che
interagiscano con il DOM.

```javascript
app.directive('clickLogger', function () {
  return {
    restrict: 'A',
    link: function (scope, el, attr) {
      el.on('click', function () {
        console.log('cliccato');
      });
    }
  };
});
<div click-logger>test</div>
```


----


filtri
------
I filtri sono funzioni utilizzabili nelle espressioni che permettono di
modificare i dati da visualizzare (eg. valute, date, upperCase,
ordinamento, etc...)

```
{{expression | filter1 | filter2}}
{{15 | currency:'€'}} // 15.00€
{{2014-10-19 | date}} // Oct 19, 2014
{{text | limitTo:n}} // mostra primi n caratteri
```

[etc](https://docs.angularjs.org/api/ng/filter)


----


Creare nuovi filtri
-------------------
Un filtro non è che una funzione che dato un input restituisce un
output ed implementarli non è quindi complicato.

```
app.filter('filterName', function () {
  return function (input, arg1, arg2) {
    ...
    return output
  },
});
{{input | filterName:arg1:arg2}}
```


---


ESERCIZI
========


----


Random color
------------
Creare una direttiva di tipo attributo chiamata random-bg-color che
accetti come attributo una lista di colori. Cliccando sull'elemento cui
verrà applicata, esso dovrà cambiare randomicamente colore tra quelli
forniti.


----


Reverse
-------
Scrivere un filtro reverse che inverte una stringa
