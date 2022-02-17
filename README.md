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
