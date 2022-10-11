<script>
  import Logo from './Logo.svelte'
  import Searcher from './Searcher.svelte'
</script>

<div class="Header">
  <Logo appName="Notitas" />
  <Searcher />
</div>

<style>
  .Header {
    width: 100%;
    display: flex;
    align-items: center;
    flex-direction: column;
  }
</style>
