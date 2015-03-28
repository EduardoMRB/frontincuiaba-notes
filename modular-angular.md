# Modular AngularJS

## Por que angularjs?
* Data binding
* Dependency Injection
* Directives

## Data binding
* AngularJS usa __Two Way Data Binding__
* Model -> View -> View

## Dependency Injection
* Dependencias são injetadas automaticamente pelo angular

```javascript
// otherApp is another angular module that was injected automatically
var app = angular.module("fooApp", ["otherApp"]);

// $scope is a angular service injected automatically aswell
app.controller("BarController", ["$scope", function ($scope) {
  $scope.greet = function (greeting) {
    console.log(greeting);
  };
}]);
```

## Directives
> HTML as HTML extension.

São "templates" semanticos para declarar componenetes reusáveis.

## Erros de arquitetura em um app angular
* Controllers com muitas responsabilidades (SRP)
* Falta de modulos
* Nome de arquivos de acordo com o tipo (controllers.js, directives.js, services.js)

## Dicas para modularização
* Separar arquivos por comportamento (todo/todoController.js ...)
* Separar comportamentos diferentes em modulos
* [ngModules](http://ngmodules.org)
* Use generators
