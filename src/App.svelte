<script>
  import Header from './components/Header.svelte'
  import Dashboard from './components/Dashboard.svelte'
  import { v4 } from 'uuid'

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
  function generateColor() {
    const color = [
      '#FFF8EA',
      '#CDFCF6',
      '#C8DBBE',
      '#DFD3C3',
      '#FFD1D1',
      '#AEBDCA',
      '#AAC4FF',
    ]
    const index = Math.floor(Math.random() * color.length)
    return color[index]
  }
  function handleNew() {
    const color = generateColor()
    const id = v4()
    const note = {
      id: id,
      title: '',
      color: color,
      text: '',
    }
    notes = [note, ...notes]
    copyNotes = [...notes]
  }
</script>

<main>
  <Header />
  <Dashboard notes={notes} on:click={handleNew} />
</main>

<style>
</style>
