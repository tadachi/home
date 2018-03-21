<template>
  <div id="app" class='grid-container'>
    <header>
      header
      <!-- Header content -->
    </header>
  
    <nav>
      <!-- Navigation -->
    </nav>
  
    <main>
      <!-- Main content -->
      <div class="nav-flex">
        <div class="nav-margin"><nuxt-link to="/">Index</nuxt-link></div>
        <div class="nav-margin"><nuxt-link to="/blog">Blog</nuxt-link></div> 
      </div>


      <nuxt/>
    </main>
  
    <aside>
      <!-- Sidebar / Ads -->
    </aside>
  
    <footer>
      footer
      <div v-bind:style="{ width: '20px' }"></div>
      <div>made with Nuxt.js and Vue</div>
      
      <!-- Footer content -->
    </footer>
  </div>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
    AppLogo,
  },
}
</script>

<style lang="scss">
@media (min-width: 0px) {
  .grid-container {
    display: grid;
    grid-template-areas:
      'header header'
      'content content'
      'footer footer';
    grid-template-columns: 1fr 6fr;
    grid-template-rows: 1fr 6fr 1fr;
    height: 100vh;
  }
}

@media (min-width: 800px) {
  .grid-container {
    grid-template-columns: 1fr 6fr 1fr;
    grid-template-rows: 1fr 6fr 1fr;
    grid-template-areas:
      'nav header  aside'
      'nav content aside'
      'nav content aside'
      'nav footer  aside';
  }
}

header {
  grid-area: header;
  border: 1px solid red;
}

nav {
  grid-area: nav;
  margin-left: 0.5rem;
  border: 1px solid red;
}

main {
  grid-area: content;
  border: 1px solid red;
}

aside {
  grid-area: aside;
  margin-right: 0.5rem;
  border: 1px solid red;
}

footer {
  grid-area: footer;
  border: 1px solid red;
}

.nav-flex {
  display: flex;
  flex-direction: row;
}

.nav-margin {
  margin-left: '10px';
}
</style>
