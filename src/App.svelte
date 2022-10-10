<script>
  import Header from './components/Header.svelte'
  import Dashboard from './components/Dashboard.svelte'

  let notes = [
    {
      id: 0,
      title: 'Vacaciones',
      color: 'yellow',
      text: 'hello',
    },
    
  ]
  let copyNotes = [...notes]
  let count = notes.length
</script>

<main>
  <Header />
  <div>
    {count} notas
  </div>
  <Dashboard />
</main>

<style>
</style>
