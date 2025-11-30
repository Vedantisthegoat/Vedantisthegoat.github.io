<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Vedant's About Me</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(to bottom, #a0eaff, #ffffff);
      overflow: hidden;
      margin: 0;
      padding: 0;
    }

    h1, p {
      text-align: center;
    }

    /* Walking ducks */
    .duck {
      position: absolute;
      bottom: 0;
      width: 50px;
      transition: transform 0.1s linear;
    }

    /* Flying ducks */
    .flying-duck {
      position: absolute;
      width: 50px;
      transition: transform 0.1s linear;
    }

    /* Monkeys climbing */
    .monkey {
      position: absolute;
      width: 60px;
      transition: transform 0.1s linear;
    }
  </style>
</head>
<body>
  <h1>Hi, I'm Vedant</h1>
  <p>I like soccer, video games, and running.</p>
  <p>I play for Cupertino FC, love Barcelona, support Man City, hate Man United.</p>
  <p>I love Minecraft and Fortnite!</p>
  <p>Press SPACE for monkeys, R for flying ducks, M for more flying ducks, 4 for games!</p>

  <script>
    // Utility function to create animal images
    function createAnimal(src, className, x = 0, y = 0) {
      const img = document.createElement('img');
      img.src = src;
      img.className = className;
      img.style.left = x + 'px';
      img.style.top = y + 'px';
      document.body.appendChild(img);
      return img;
    }

    // Walking ducks
    const walkingDucks = [];
    for (let i = 0; i < 5; i++) {
      walkingDucks.push(createAnimal(
        'https://i.imgur.com/1yFzA8Q.png', // small duck image
        'duck',
        i * 100,
        window.innerHeight - 80
      ));
    }

    // Animate walking ducks
    setInterval(() => {
      walkingDucks.forEach(duck => {
        let left = parseInt(duck.style.left);
        left += 2;
        if (left > window.innerWidth) left = -50;
        duck.style.left = left + 'px';
      });
    }, 50);

    // Keypress actions
    document.addEventListener('keydown', function(event) {
      if (event.key === ' ') { // monkeys climbing
        const monkey = createAnimal(
          'https://i.imgur.com/FrUZfTh.png', // monkey image
          'monkey',
          Math.random() * (window.innerWidth - 60),
          window.innerHeight - 80
        );
        let top = parseInt(monkey.style.top);
        const climb = setInterval(() => {
          top -= 5;
          monkey.style.top = top + 'px';
          if (top < -60) {
            clearInterval(climb);
            monkey.remove();
          }
        }, 50);
      }

      if (event.key.toLowerCase() === 'r' || event.key.toLowerCase() === 'm') { // flying ducks
        const fduck = createAnimal(
          'https://i.imgur.com/1yFzA8Q.png', 
          'flying-duck',
          Math.random() * (window.innerWidth - 50),
          window.innerHeight - 80
        );
        let top = parseInt(fduck.style.top);
        const fly = setInterval(() => {
          top -= 8;
          fduck.style.top = top + 'px';
          if (top < -50) {
            clearInterval(fly);
            fduck.remove();
          }
        }, 50);
      }

      if (event.key === '4') { // go to DuckMath games
        window.location.href = 'https://duckmath.org/';
      }
    });
  </script>
</body>
</html>
