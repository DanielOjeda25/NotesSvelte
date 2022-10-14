<script>
  export let notes
  import { each } from 'svelte/internal'
  import Note from './Note.svelte'
  import NotePlaceholder from './NotePlaceholder.svelte'
</script>

<div class="Dashboard">
  <div class="notes-container">
    <NotePlaceholder on:click />
    {#each notes as { title, color, text, id }}
      <Note bind:title={title} {color} bind:text={text} {id} on:update on:color on:remove />
    {/each}
  </div>
</div>

<style>
  .Dashboard {
    width: 100%;
    padding: 20px;
    box-sizing: border-box;
  }
  .notes-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    width: 100%;
    gap: 10px;
  }
</style>
