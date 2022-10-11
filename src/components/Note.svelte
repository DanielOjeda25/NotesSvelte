<script>
  export let text
  export let title
  export let color
</script>

<div class="Note">
  <div class="note-container">
    <div class="header">
      <div class="options">
        <button>Color</button>
        <button>Eliminar</button>
      </div>
    </div>
    <div class="content">
      <div class="title">
        <input
          type="text"
          name=""
          id=""
          placeholder="Sin titulo"
          bind:value={title}
        />
      </div>
      <div class="text">
        <textarea
          name=""
          id=""
          cols="30"
          rows="10"
          placeholder="Agregue una nota"
          bind:value={text}
        />
      </div>
    </div>
  </div>
  {title}
  {color}
  {text}
</div>

<style>
  .Note {
    background-color: white;
    border-radius: 3px;
    border: solid 2px transparent;
    overflow: hidden;
    height: 400px;
    border: 1px solid black;
  }
  .note-container {
    height: 100%;
  }
  .note-container:focus-within {
    border: solid 1px #000;
    box-shadow: 0 2px 5px  rgba(0, 0, 0, 0.066);
  }
  .Note .note-container .header {
    padding: 5px;
  }
  .header .options {
    display: flex;
    justify-content: space-between;
  }
  .Note .content {
    padding: 0 20px;
  }
  .text textarea {
    width: 100%;
    border: 0;
    outline: none;
    resize: none;
    height: 15.625rem;
  }
  .title input {
    font-size: 1.375rem;
    font-weight: bold;
    padding: 10px 0;
    outline: none;
    border: none;
    width: 100%;
  }
  button {
    margin: 0;
    border: none;
    background-color: transparent;
    cursor: pointer;
  }
  textarea,
  input {
    background: transparent;
  }
</style>
