<script lang="ts">
  import Header from './lib/Header.svelte'
  import Projects from './lib/Projects.svelte';
  import 'framework7-icons/css/framework7-icons.css'
</script>

<main>
<Header></Header>

<Projects></Projects>
</main>

<style global lang="scss">
  @import './styles/global.scss';
  :root {
    font-family: Inter;
  }

  html, body {
    margin:0;
    background: #f6f6f6;
  }

  @media(prefers-color-scheme: dark) {
    html, body {
      background: #1c1c1c;
    }
  }
  
</style>
