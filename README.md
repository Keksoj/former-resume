# Mon CV en ligne

Finalement, je me débrouille en CSS ! Je suis fan de [flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/), qui permet de faire du responsive à peu de frais.

Flexbox permet d'organiser des items dans un container. Chaque section de mon CV est un container que j'ai appelé `section`, et qui contient deux items :

1. `section-title` qui contient le logo et le titre de la section
2. `section-content` qui contient le texte ou le tableau de la section

```html
<div id="parcours" class="section put_the_logo_to_the_right">
    <div class="section-title">
        <img class="section-logo" src="img/path.svg" />
        <h2 class="h2-title">Un parcours riche</h2>
    </div>

    <div class="section-content">
        <!-- contenu -->
    </div>
</div>
```

```css
.section {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    margin: 0;
    list-style: none;
}

.put_the_logo_to_the_left {
    flex-direction: row;
    flex-wrap: wrap;
}

.put_the_logo_to_the_right {
    flex-direction: row-reverse;
    flex-wrap: wrap;
}
.section-title {
    /*  rien de particulier */
}
.section-content {
    width: 600px;
}
```

Le CSS `flex-direction: row-reverse` affiche la div `section-title` à droite de `section-content`, contrairement à l'ordre du HTML. La propriété `flex-wrap: wrap` fait que si l'écran n'est pas assez large, les deux divs sont empilées l'une sur l'autre, dans l'ordre du HTML cette fois.
C'est plutôt pratique.
