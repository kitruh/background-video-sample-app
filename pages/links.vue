<template>
    <div class="link-component">
      <div class="link-wrapper">
        <a href="https://kitruh.bandcamp.com/">bandcamp</a>
      </div>
      <div class="link-wrapper">
        <a href="https://open.spotify.com/artist/1F8vwvUFQrG3b3LeOVvYT5">Spotify</a>
      </div>
      <div class="link-wrapper">
        <a href="https://www.instagram.com/kitruh_/">Instagram</a>
      </div>
      <div class="link-wrapper">
        <a href="https://music.apple.com/us/artist/kitruh/1459583434">iTunes</a>
      </div>
    </div>
</template>

<script>
  export default {
    name: 'links'
  }
</script>

<style scoped>
  .link-wrapper{
    width:100%;
    background-color: #00faff;;
    display:flex;
    justify-content:center;
    align-items: center;
    height:2em;
    font-family: 'Open Sans', sans-serif;
    font-weight: 800;
    font-size:3em;
  }
  a{
    color:white;
    text-decoration:none;
    cursor:pointer;
  }
</style>
