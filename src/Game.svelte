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

  let playerY = 180;
</script>

<div class="game">
  <World {objects} />
  <div class="player" style="bottom: {playerY}px">🏃🏻‍♂️</div>
</div>
