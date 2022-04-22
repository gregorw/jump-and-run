<script>
  import World from './World.svelte';
	const units = 10;
  const size = 35;

  const objects = [
    null,
    null,
    null,
    null,
    null,
    null,
    null,
    ['🛢','🛢'],
    ['🛢','🛢'],
    null,
    null,
    null,
    null,
    null,
    null,
    null,
    ['☮️','☮️'],
    ['☮️','☮️', '☮️'],
    ['☮️','☮️'],
    null,
    null,
    null,
    ['🌵'],
    ['🌵'],
    null,
    null,
    null,
    null,
    null,
    null,
    null,
    null,
    null,
    null,
    ['🏁'],
    null,
    null,
    null,
    null,
    null,
    null,
    null,
    ['💯'],
  ]

  let speed = 0.2

  let playerY;
  let playerX;
  let time;
  let started;

  const reset = function() {
    time = 0;
    playerX = size;
    playerY = 0;
    started = false;
  }
  reset();

  const worldSize = objects.length * size;
  const gameSize = units * size;
  let interval = null

  const start = function() {
    interval = setInterval(step, 1 / speed);
    started = true;
  }

  const step = function() {
    if (time < worldSize - gameSize) {
      time += 1;
    } else {
      clearInterval(interval);
      alert('You win!');
      walkHome();
    }
  }

  const walkHome = function() {
    const walk = function() {
      playerX = playerX + 1;
      if (playerX < gameSize) {
        setTimeout(walk, .5 / speed);
      } else {
        reset();
      }
    }
    walk();
  }
</script>

<div class="center">
  <button disabled={started} on:click={start}>Start</button>
</div>

<div class="game">
  <div class="player" style="bottom: {playerY}px; left: {playerX}px">🏃🏻‍♂️</div>
  <World {objects} {time} />
</div>

<style>
  button { font-size: 2rem; }
</style>
