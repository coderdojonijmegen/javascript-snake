---
title: "Javascript - Snake - einde instructie"
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
        h1 {
            text-align: center;
        }
    </style>
</head>
<body>
<h1>Snake</h1>
<div class="snakearea">
    <canvas id="speelveld" width="800" height="800"></canvas>
    <div style="display: none;">
        <img id="appel" src="data:image/png;base64,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" >
    </div>
</div>
<script>
    const speelveld = document.getElementById("speelveld");
    const ctx = speelveld.getContext("2d");

    const vakGrootte = 25;
    const appelGrootte = vakGrootte * 1.2;
    const aantalVakjes = speelveld.width / vakGrootte;

    const appel = { x: 0, y: 0 };
    const slang = [{ x: 10, y: 10 }];

    let richting = "rechts";

    const appelPlaatje = document.getElementById("appel");
    function tekenAppel() {
        ctx.drawImage(appelPlaatje, appel.x * vakGrootte, appel.y * vakGrootte, appelGrootte, appelGrootte);
    }

    function tekenSlang() {
        for (let slangDeel of slang) {
            ctx.fillStyle = "green";
            ctx.fillRect(slangDeel.x * vakGrootte, slangDeel.y * vakGrootte, vakGrootte - 1, vakGrootte - 1);
        }
    }

    function toonGameOver() {
        ctx.fillStyle = "orange";
        ctx.font = "75px Arial";
        ctx.fillText("Game over!", 200, 400);
    }

    let score = 0;
    function toonScore() {
        ctx.fillStyle = "black";
        ctx.font = "30px Arial";
        ctx.fillText(`Score ${score}`, 350, 30);
    }

    function nieuwePlaatsAppel() {
        appel.x = Math.floor(Math.random() * aantalVakjes);
        appel.y = Math.floor(Math.random() * aantalVakjes);
    }

    function verplaatsSlang() {
        const nieuweSlangenKop = {...slang[0]};
        switch (richting) {
            case "omhoog": nieuweSlangenKop.y -= 1; break;
            case "omlaag": nieuweSlangenKop.y += 1; break;
            case "links": nieuweSlangenKop.x -= 1; break;
            case "rechts": nieuweSlangenKop.x += 1; break;
        }
        slang.unshift(nieuweSlangenKop);
        if (nieuweSlangenKop.x === appel.x && nieuweSlangenKop.y === appel.y) {
            nieuwePlaatsAppel();
            score += 1;
        } else {
            slang.pop();
        }
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

    function slangHeeftZichzelfGeraakt() {
        const slangenKop = slang[0];
        for (let slangDeel of slang.slice(1)) {
            if (slangDeel.x === slangenKop.x && slangDeel.y === slangenKop.y) {
                return true;
            }
        }
        return false;
    }

    function slangHeeftEenRandGeraakt() {
        const slangenKop = slang[0];
        return slangenKop.x < 0 || slangenKop.x >= aantalVakjes || slangenKop.y < 0 || slangenKop.y >= aantalVakjes;
    }

    function isGameOver() {
        return slangHeeftZichzelfGeraakt() || slangHeeftEenRandGeraakt();
    }

    function gameLoop() {
        if (isGameOver()) {
            toonGameOver();
            return;
        }
        maakSpeelveldLeeg();
        verplaatsSlang();
        tekenAppel();
        tekenSlang();
        toonScore();
    }

    nieuwePlaatsAppel();
    setInterval(gameLoop, 100);
</script>
</body>
</html>
```
