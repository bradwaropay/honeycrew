<template>
  <div class="app">
    <header class="app__header">
      <page-title />
    </header>
    <main class="app__main">
      <nuxt />
    </main>
    <footer class="app__footer">
      <p>Generator by <a href="https://bradwaropay.com">Brad Waropay</a> | Based on <a href="https://gshowitt.itch.io/honey-heist">Honey Heist</a>, a game by <a href="https://gshowitt.itch.io/">Grant Howitt</a></p>
    </footer>
  </div>
</template>

<script>
import PageTitle from '~/components/PageTitle.vue'

export default {
  components: {
    PageTitle
  }
}
</script>

<style lang="postcss">
html,
body,
#__nuxt,
#__layout,
.app {
  height: 100%;
}

html,
body {
  margin: 0;
  padding: 0;
}

body {
  background-color: orange;
  color: black;
  font-family: 'Architects Daughter', cursive;
  text-transform: uppercase;
}

* {
  box-sizing: border-box;
}

a {
  color: orangered;
  text-decoration: none;
}

.bold {
  font-family: 'Chelsea Market', cursive;
}

.app {
  display: grid;
  grid-template-rows: auto 1fr auto;

  &__header,
  &__footer {
    padding: 2rem;
    z-index: 1000;
  }

  &__main {
    align-items: center;
    display: flex;
    justify-content: center;
  }
}
</style>
