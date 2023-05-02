<svelte:options tag="responsive-tester" />

<script>
  let width = "50";
  export let url = "https://alexrdz.me/";

  function handleRangeChange(e) {
    width = e.target.value;
  }

  function handleUrlChange(e) {
    url = e.target.value;
  }
</script>

<div>
  <input type="text" value={url} on:input={handleUrlChange} />

  <input
    type="range"
    min="30"
    max="100"
    value={width}
    on:input={handleRangeChange}
  />

  <iframe title="iframe" src={url} style={`width: ${width}%`} />
</div>

<style>
  div {
    padding: 1rem;
  }
  input {
    display: block;
    padding: 1rem;
    min-width: 380px;
    max-width: 100%;
  }

  iframe {
    border: none;
    min-height: 80vh;
    height: 100%;
  }
</style>
