---
title: "Javascript - Snake - tot en met opdracht 4"
date: 2025-10-19T10:51:01+02:00
draft: false
toc: false
headercolor: "teal-background"
onderwerp: Javascript 
---
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
            border: 1px solid black;
        }
    </style>
</head>
<body>
<h1>Snake</h1>
<div class="snakearea">
    <canvas id="speelveld" width="800" height="800"></canvas>
</div>
<script>
    const speelveld = document.getElementById("speelveld");
    const ctx = speelveld.getContext("2d");

    const vakGrootte = 25;
    const appelGrootte = vakGrootte / 2 + 1;
    const aantalVakjes = speelveld.width / vakGrootte;

    const appel = { x: 0, y: 0 };
    const slang = [{ x: 10, y: 10 }];

    let richting = "rechts";

    function tekenAppel() {
        ctx.fillStyle = "red";
        ctx.beginPath();
        ctx.arc(appel.x * vakGrootte + appelGrootte, appel.y * vakGrootte + appelGrootte, appelGrootte, 0, 2 * Math.PI);
        ctx.fill();
    }

    function tekenSlang() {
        for (let slangDeel of slang) {
            ctx.fillStyle = "green";
            ctx.fillRect(slangDeel.x * vakGrootte, slangDeel.y * vakGrootte, vakGrootte - 1, vakGrootte - 1);
        }
    }

    function verplaatsSlang() {
        const head = {...slang[0]};
        switch (richting) {
            case "omhoog": head.y -= 1; break;
            case "omlaag": head.y += 1; break;
            case "links": head.x -= 1; break;
            case "rechts": head.x += 1; break;
        }
        slang.unshift(head);
        slang.pop();
    }

    document.addEventListener("keydown", (event) => {
        switch (event.key) {
            case "ArrowUp": richting = "omhoog"; break
            case "ArrowDown": richting = "omlaag"; break
            case "ArrowLeft": richting = "links"; break
            case "ArrowRight": richting = "rechts"; break
            case "o": document.location.reload(); break
        }
        console.log(richting);
    });

    function maakSpeelveldLeeg() {
        ctx.clearRect(0, 0, speelveld.width, speelveld.height);
    }

    function gameLoop() {
        maakSpeelveldLeeg();
        verplaatsSlang();
        tekenAppel();
        tekenSlang();
    }

    setInterval(gameLoop, 100);
</script>
</body>
</html>
```
