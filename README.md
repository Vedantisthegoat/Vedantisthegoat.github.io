<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Vedant's Page</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background: linear-gradient(#a8e6ff, #ffffff);
        overflow-x: hidden;
        height: 100vh;
    }

    h1 {
        text-align: center;
        font-size: 2.5rem;
    }

    .bio {
        text-align: center;
        font-size: 1.4rem;
    }

    /* Duck walking */
    .duck {
        position: absolute;
        width: 80px;
        bottom: 0;
        animation: walk 10s linear infinite;
    }

    @keyframes walk {
        from { left: -100px; }
        to { left: 110%; }
    }

    /* Flying duck */
    .flying {
        position: absolute;
        width: 80px;
        animation: fly 6s linear forwards;
    }

    @keyframes fly {
        from { transform: translate(-200px, 200px) rotate(10deg); }
        to { transform: translate(120vw, -200px) rotate(-20deg); }
    }

    /* Monkey climbing */
    .monkey {
        position: absolute;
        width: 100px;
        left: 0;
        animation: climb 6s linear forwards;
    }

    @keyframes climb {
        from { bottom: -150px; transform: translateX(-50px); }
        to { bottom: 100vh; transform: translateX(40px); }
    }
</style>
</head>
<body>

<h1>Welcome to Vedant's GitHub Page!</h1>

<div class="bio">
    <p>My name is <strong>Vedant</strong></p>
    <p>I like soccer, video games, and running</p>
    <p>I play for <strong>Cupertino FC</strong></p>
    <p>I love and support <strong>Barcelona</strong></p>
    <p>I support <strong>Man City</strong> and hate <strong>Man United</strong></p>
    <p>I love Minecraft & Fortnite</p>
    <p><strong>Press 4 to go to my Games!</strong></p>
</div>

<!-- Moving Ducks -->
<img src="https://i.imgur.com/4NJl8yX.png" class="duck" style="animation-delay:0s;">
<img src="https://i.imgur.com/4NJl8yX.png" class="duck" style="animation-delay:3s;">
<img src="https://i.imgur.com/4NJl8yX.png" class="duck" style="animation-delay:6s;">

<script>
// -------------------------------
// KEYBOARD CONTROLS
// -------------------------------

document.addEventListener("keydown", function(e) {

    // Press R = Flying ducks
    if (e.key === "r" || e.key === "R") {
        spawnFlyingDuck();
    }

    // Press SPACE = Monkeys climbing
    if (e.key === " ") {
        spawnMonkey();
    }

    // Press 4 = Go to games.html page
    if (e.key === "4") {
        window.location.href = "games.html";
    }
});

// -------------------------------
// SPAWN FLYING DUCK
// -------------------------------
function spawnFlyingDuck() {
    let duck = document.createElement("img");
    duck.src = "https://i.imgur.com/4NJl8yX.png";
    duck.className = "flying";
    duck.style.top = Math.random() * 300 + "px";
    duck.style.left = "-150px";
    document.body.appendChild(duck);

    setTimeout(() => duck.remove(), 6000);
}

// -------------------------------
// SPAWN MONKEY
// -------------------------------
function spawnMonkey() {
    let monkey = document.createElement("img");
    monkey.src = "https://i.imgur.com/ZY6Ew0P.png";
    monkey.className = "monkey";
    monkey.style.left = Math.random() * (window.innerWidth - 150) + "px";
    document.body.appendChild(monkey);

    setTimeout(() => monkey.remove(), 6000);
}
</script>

</body>
</html>
