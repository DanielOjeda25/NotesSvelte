<script>
  export let text
  export let title
  export let color
</script>

<div class="Note">
  <div class="note-container" style={`background-color: ${color}`}>
    <div class="header">
      <div class="options">
        <button
          ><svg class="svg-icon" viewBox="0 0 20 20">
            <path
              fill="none"
              d="M10,4.75c-5.316,0-9.625,4.505-9.625,10.062c0,0.241,0.196,0.438,0.438,0.438h7.875c0.242,0,0.438-0.196,0.438-0.438c0-0.725,0.392-1.312,0.875-1.312s0.875,0.588,0.875,1.312c0,0.241,0.195,0.438,0.438,0.438h7.875c0.242,0,0.438-0.196,0.438-0.438C19.625,9.255,15.316,4.75,10,4.75 M11.715,14.375c-0.162-0.998-0.868-1.75-1.715-1.75s-1.553,0.752-1.715,1.75H6.523c0.193-1.968,1.676-3.5,3.477-3.5c1.801,0,3.284,1.532,3.477,3.5H11.715z M14.354,14.375C14.153,11.923,12.282,10,10,10s-4.154,1.923-4.355,4.375h-1.75C4.106,10.957,6.755,8.25,10,8.25s5.894,2.707,6.104,6.125H14.354zM16.979,14.375c-0.214-3.902-3.252-7-6.979-7s-6.765,3.098-6.979,7h-1.75C1.49,9.505,5.308,5.625,10,5.625c4.691,0,8.51,3.88,8.729,8.75H16.979z"
            /></svg
          ></button
        >
        <button
          ><svg class="svg-icon" viewBox="0 0 20 20">
            <path
              d="M17.114,3.923h-4.589V2.427c0-0.252-0.207-0.459-0.46-0.459H7.935c-0.252,0-0.459,0.207-0.459,0.459v1.496h-4.59c-0.252,0-0.459,0.205-0.459,0.459c0,0.252,0.207,0.459,0.459,0.459h1.51v12.732c0,0.252,0.207,0.459,0.459,0.459h10.29c0.254,0,0.459-0.207,0.459-0.459V4.841h1.511c0.252,0,0.459-0.207,0.459-0.459C17.573,4.127,17.366,3.923,17.114,3.923M8.394,2.886h3.214v0.918H8.394V2.886z M14.686,17.114H5.314V4.841h9.372V17.114z M12.525,7.306v7.344c0,0.252-0.207,0.459-0.46,0.459s-0.458-0.207-0.458-0.459V7.306c0-0.254,0.205-0.459,0.458-0.459S12.525,7.051,12.525,7.306M8.394,7.306v7.344c0,0.252-0.207,0.459-0.459,0.459s-0.459-0.207-0.459-0.459V7.306c0-0.254,0.207-0.459,0.459-0.459S8.394,7.051,8.394,7.306"
            />
          </svg></button
        >
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
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.066);
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
  .svg-icon {
    width: 2em;
    height: 2em;
  }

  .svg-icon path {
    fill: #0e0e0e;
  }
 
</style>
