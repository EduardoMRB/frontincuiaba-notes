# Esse cara é o grunt

> O rei do workflow front-end

* Automatizador de tarefas
* Linha de comando
* NodeJS

## Grunt não é o único
O grunt não é revolucionário, existem vários build tools:

* Make
* Ant
* Rake
* Cake
* Broccoli
* Gulp
* Boot
* Leiningen
* ...

## Por que usar o grunt?
* Evitar trabalho repetitivo
* Evitar erros
* Muitos detalhes para lembrar

## Environments

### Dev
* Rodar testes
* Preprocessadores
* Linting
* Web server
* scaffolding
* Criar Sprites
* Live reloading

### Prod
* Otimizar imagens
* Concatenação
* Preprocessamento
* Minificação (Uglify)
* Release
* Deploy

## Iniciando com o grunt

### Dependencias
* NodeJS
* npm

### Instalação
```shell
$ npm install --global grunt-cli
```

### Configuração
No arquivo ``package.json``

### Gruntfile.js
Onde as tasks do **grunt** são escritas.

```javascript
module.exports = function (grunt) {
  grunt.initConfig({
    uglify:  {
      build: {
        src: "dist/app.js",
        dest: "dist/app.min.js"
      }
    },
    jasmine: {
      src: "assets/js/**/*.js",
      options: {
        specs: "spec/*Spec.js",
        helpers: "spec/*Helper.js"
      }
    },
    concat: {
      options: {
        separator: ";"
      },
      dist: {
        src: ["assets/js/a.js", "assets/js/e.js"],
        dest: ["dist/app.js"]
      }
    },
    compass: {
      // $ grunt compass:dev
      dev: {
        options: {
          sassDir: "assets/scss",
          cssDir: "dist/css",
          imagesDir: "assets/images",
          generatedImagesDir: "dist/images"
        }
      },
      // $ grunt compass:prod
      prod: {
        options: {
          outputStyle: "compressed"
        }
      }
    }
  });

  grunt.loadNpmTasks("grunt-contrib-uglify");
  grunt.loadNpmTasks("grunt-contrib-compass");
  grunt.loadNpmTasks("grunt-contrib-jasmine");

  // Registrar uma task que vai ser disponível por linha de comando
  // $ grunt build
  grunt.registerTask("build", [
    "uglify",
    "jasmine"
  ]);

  // Registrar task padrão
  // $ grunt
  grunt.registerTask("default", ["build"]);
}
```

## Impressões
* Tasks em Coffeescript
* Template engine do grunt
* Flexibilidade para definir e estender tasks
* Tasks em concorrencia
