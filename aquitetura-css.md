# Arquitetura CSS

## Pra que padrões?
* Muito se fala sobre design patterns em linguagens de programação, mas e o CSS?
* Pensar na manutenção do código

## Metodologias

### OOCSS - CSS orientado a objetos
Baseado em metodologias usadas em várias linguagens de programação.

> Ex: Botões de vários tamanhos e cores utilizando a mesma classe base

### SMACSS
Criado pelo Yahoo! para resolver problemas de CSS no Yahoo! Mail.

#### Cinco Categorias

##### Base
* Sem seletores com classes ou ids
* CSS Reset ou normalize.css

##### Layout
* Toda estrutura não repetida do projeto

##### Module
* Componentes (botões, tabs, etc)

##### State
* Tudo que é estado da aplicação (is-active, is-collapse, is-blocked)

##### Theme
Construtures para aplicaçãoes que mudam o tema dinamicamente.

### BEM (Block Element Modifier)
Nasceu de um projeto criado pelo time de front end da Yandex.

```css
/* Elemento pai */
.formcontent {}

/* Elemento filho */
.formcontent__field {}

/* Elemento filho modificado */
.formcontent__field--first {}
```

## Arquitetura de aplicação + vendor lib
Verificar se a lib tem uma versão preprocessada e realizar as mudanças a partir daí.
