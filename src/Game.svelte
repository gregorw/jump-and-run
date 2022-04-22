<script>
  import World from './World.svelte';
	const units = 10;

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

  const start = function() {
    setInterval(step, 10);
  }

  const step = function() {
    time = time + 2;
  }
</script>

<div class="center">
  <button on:click={start}>Start</button>
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
