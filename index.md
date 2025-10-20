---
title: "Javascript - Snake"
date: 2025-10-19T10:51:01+02:00
draft: false
toc: true
headercolor: "teal-background"
onderwerp: Javascript 
---

We gaan Snake bouwen voor in de browser.

<!--more-->

## Introductie

## Wat heb je nodig?

## Instructie

### 1. HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Snake</title>
    <style>
        canvas {
            display: block;
            margin: 0 auto;
        }
    </style>
</head>
<body>
<div class="snakearea">
    <canvas id="playground" width="800" height="800"></canvas>
</div>
</body>
</html>
```

### 2. Een appel

Voeg toe op regel 17 in de vorige code:
```html
<script>
</script>
```
En tussen de `<script>` en `</script>` tags:

```javascript
    const elemPlayground = document.getElementById("playground");
    const ctx = elemPlayground.getContext("2d");

    const boxSize = 25;
    const foodSize = boxSize / 2 + 1;
    const numBoxes = elemPlayground.width / boxSize;

    const food = { x: 0, y: 0 };

    function drawFood() {
        ctx.fillStyle = "red";
        ctx.beginPath();
        ctx.arc(food.x * boxSize + foodSize, food.y * boxSize + foodSize, foodSize, 0, 2 * Math.PI);
        ctx.fill();
    }

    drawFood();
```
## Uitdagingen

> Te doen:
> 1. Pas [FrontMatter](https://gohugo.io/content-management/front-matter/) aan boven in dit bestand.
>    - `title` naar een passende titel bij deze instructie
>    - `data` naar vandaag
>    - `onderwerp` naar de gebruikte techniek aanpassen, bijvoorbeeld Python (wordt gebruikt om te sorteren per onderwerp)
> 2. Denk qua structuur aan:
>   - Introductie van het onderwerp
>   - Wat heb je nodig (programma's/materialen)
>   - De instructie zelf verdeelt over stappen; het is fijn als kinderen per stap al resultaat kunnen zien
>   - Afronding met bijvoorbeeld uitdagingen op basis van het geleerde en/of linkjes naar pagina's met nog meer informatie over het onderwerp
> 3. Laat onderstaande licentie staan
> 
> Bekijk [deze uitleg](https://github.com/coderdojonijmegen/hugo-coderdojo-nijmegen/blob/main/README.md) over hoe je kunt zien
> hoe je instructies er uit zien in de site.  

{{< licentie rel="http://creativecommons.org/licenses/by-nc-sa/4.0/">}}
