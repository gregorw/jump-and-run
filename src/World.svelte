<script>
	export let objects = [];


</script>

<div class="world">
  {#each objects as column, i}
    <div class="column">
      {#each column || [] as object}
        <div class="object">{object}</div>
      {/each}
    </div>
	{/each}
</div>
