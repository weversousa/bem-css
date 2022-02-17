## CSS Externo

```css
/* style.css */
body {
    background-color: aqua;
}
```

```html
<head>
    <link rel="stylesheet" href="./style.css">
</head>

<body>
</body>
```


## CSS Interno

```html
<head>
    <style>
        body { background-color: aqua; }
    </style>
</head>

<body>
</body>
```


## CSS Inline

```html
<body style="background-color: aqua;">
</body>
```


## Seletor

### Adjacente

Verificar se uma `div` tem algum **vizinho** `div` *antes* dela.

```css
div + div {}
```

```html
<main>
    <div>div 1</div>
    <div>Afetado</div>
</main>
```

### Irmãos

Verificar se o `span` tem algum **irmão** `p` *antes* dele.

```css
p ~ span {}
```

```html
<div>
    <p></p>
    <span>Afetado</span>
</div>

<section>
    <p></p>
    <span>Afetado</span>
</section>
```

### Filhos diretos

```css
section > div {}

```

```html
<section>
    <div>Afetado</div>
    <div>Afetado</div>

    <ul>
        <li>
            <div></div>
        </li>
    </ul>
</section>
```

### Descendente

```css
section div {}

```

```html
<section>
    <div>Afetado</div>
    <div>Afetado</div>

    <ul>
        <li>
            <div>Afetado</div>
        </li>
    </ul>
</section>
```

### Múltiplos

```css
li, p {}

```

```html
<section>
    <div></div>
    <div></div>

    <ul>
        <li>Afetado</li>
    </ul>
</section>

<p>Afetado</p>
```


## ID

```css
#container {}

/* ou */
div#container {}
```

```html
```


## Classe

```css
.container {}

/* ou */
div.container {}
```

```html
```


## Atributo

Selecionar todos `href`.

```css
[href] {}
```

```html
<a href="https://www.google.com.br/">Afetado</a>
<a href="https://www.youtube.com/">Afetado</a>
```

Selecionar somente `href` que contenham **google**.

```css
[href*=google] {}
```

```html
<a href="https://www.google.com.br/">Afetado</a>
<a href="https://www.youtube.com/"></a>
```

Você pode criar o seu próprio atributo.  
Selecionar todos `personalizado` que contenham exatamente **sim**.

```css
[personalizado=sim] {}
```

```html
<div personalizado="sim nao"></div>
<div personalizado="sim,nao"></div>
<div personalizado="sim">Afetado</div>
```

```css
[personalizado~=sim] {}
```

Selecionar todos `personalizado` que contenham **sim** mesmo que tenha espaço.

```html
<div personalizado="sim nao">Afetado</div>
<div personalizado="sim,nao"></div>
<div personalizado="sim">Afetado</div>
```

Selecionar todos `personalizado` que contenham **sim** independetente de qualquer coisa.

```css
[personalizado*=sim] {}
```

```html
<div personalizado="sim nao">Afetado</div>
<div personalizado="sim,nao">Afetado</div>
<div personalizado="sim">Afetado</div>
```


## Elemento

```css
div {}
```


## Tudo

```css
* {}
```


## :PSEUDO-CLASS

Selecionar o **1º** elemento `p` que seja *filho* de alguém.

```css
p:nth-child(1) {}
```

```html
    <div>
        <p>Afetado</p>
        <p></p>
    </div>

    <div>
        <p>Afetado</p>
        <p></p>
    </div>

    <main>
        <p>Afetado</p>
        <p></p>
    </main>

    <section>
        <p>Afetado</p>
        <p></p>
    </section>
```

Selecionar todos os elementos *filhos* ímpares de **ul**.

```css
ul > :nth-child(odd) {}
```

```html
<ul>
    <li>Afetado</li>
    <li></li>
    <li>Afetado</li>
    <li></li>
</ul>
```

Selecionar todos os elementos *filhos* pares de **ul**.

```css
ul > :nth-child(even) {}
```

```html
<ul>
    <li></li>
    <li>Afetado</li>
    <li></li>
    <li>Afetado</li>
</ul>
```

Selecionar a **2ª** `span` *filha* de uma `div`.

```css
div > span:nth-of-type(2) {}
```

```html
<div>
    <span>1</span>
    <p>1</p>
    <span>Afetado</span>
    <span>1</span>
</div>
```


## BEM CSS

```css
/* Bloco */
.menu {}

/* Elemento */
.menu__item {}
.menu__link {}

/* Modificador */
.menu__link--active {}
```

```html
<ul class="menu">
    <li class="menu__item">
        <a class="menu__link"></a>
    </li>
    <li class="menu__item">
        <a class="menu__link menu__link--active"></a>
    </li>
</ul>
```


## NAMESPACE

### Componente: c-

```css
.c-card {}
.c-card__title {}
.c-card__body {}
.c-card__footer {}

.c-modal {}
.c-modal__content {}
.c-modal__button {}
```

### Utilitário: u-

Tem uma única responsabilidade.  
Definido uma vez e não mais alterado  
Será utilizado múltiplas vezes no código

```css
.u-bold {
    font-weight: bold;
}

.u-total-centered {
    display: grid;
    place-items: center;
}
```

### Estado/Condição: is-/has-

```css
.c-modal {}
.c-modal.is-open {}

.c-main-menu {}
.c-main-menu.has-submenus {}
.c-main-menu.is-open {}
```

```html
<aside class="c-modal is-open"></aside>

<nav class="c-main-menu has-submenus is-open"></nav>
```

### JavaScript: js-

```javascript
const mainMenu =  document.querySelector('.js-main-menu');
```

```html
<nav class="c-main-menu js-main-menu"></nav>
```

### QA: qa-

```html
<nav class="c-main-menu qa-main-menu"></nav>
```

### Escopo (Scope): s-

```css
```
