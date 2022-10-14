<script>
  import Header from './components/Header.svelte'
  import Dashboard from './components/Dashboard.svelte'
  import { v4 } from 'uuid'
  import NotePlaceholder from './components/NotePlaceholder.svelte'
  import Note from './components/Note.svelte'

  let notes = [
    {
      id: 0,
      title: 'Vacaciones',
      color: 'yellow',
      text: 'hello',
    },
  ]
  let copyNotes = [...notes]
  $:count = notes.length 
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
  function handleUpdate(e){
    const note = e.detail
    const index = notes.findIndex(n => n.id === note.id)
    notes[index] = note
    copyNotes = [...notes]
  }
  function handleColor(e){
    const index = notes.findIndex(n => n.id === e.detail.id)
    notes[index].color = generateColor()
    copyNotes[index].color = notes[index].color
  }
  function handleRemove(e){
    const response = notes.filter(n => n.id !== e.detail.id)
    notes = [...response]
    copyNotes = [...notes]
  }
  function handleSearch(e){
    const q = e.target.value
    if (q === '') {
       copyNotes = [...notes]
       return false
    }
    const result = notes.filter(note => {
      const title = note.title.toLowerCase()
      const text = note.text.toLowerCase()
      return title.indexOf(q) > -1 || text.indexOf(q) > -1
    })
    copyNotes = [...result]
  }
</script>

<main>
  <Header on:input={handleSearch}/>
  <div class="count-notas">{count} notas</div>
  <Dashboard notes={copyNotes} on:click={handleNew} on:update={handleUpdate} on:color={handleColor} on:remove={handleRemove}/>
</main>

<style>
  .count-notas {
    padding: 20px 20px 0 20px;
    text-align: right;
  }

</style>
