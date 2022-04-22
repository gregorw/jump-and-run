<script>
	export let objects = [];
  export let time = 0;
</script>

<div class="world" style="left: -{time}px">
  {#each objects as column}
    <div class="column">
      {#each column || [] as object}
        <div class="object">{object}</div>
      {/each}
    </div>
	{/each}
</div>
