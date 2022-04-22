<script>
  import World from './World.svelte';
	const units = 10;
  const size = 60;

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
  ]

  let playerY = 200;
  let time = 0;
  let started = false;

  const worldSize = objects.length * size;
  const gameSize = units * size;
  let interval = null

  const start = function() {
    interval = setInterval(step, 5);
    started = true;
  }

  const step = function() {
    if (time < worldSize - gameSize) {
      time += 1;
    } else {
      clearInterval(interval);
      alert('You win!');
    }
  }
</script>

<div class="center">
  <button disabled={started} on:click={start}>Start</button>
</div>

<div class="game">
  <World {objects} {time} />
  <div class="player" style="bottom: {playerY}px">🏃🏻‍♂️</div>
</div>

<style>
  .center {
    text-align: center;
  }
  button { font-size: 2rem; }
</style>
