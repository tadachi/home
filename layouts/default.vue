<template>
  <div id="app" class='grid-container'>
    <header>
      <!-- Header content -->
      <div class="nav-flex">
        <div class="nav-margin"><nuxt-link to="/">Index</nuxt-link></div>
        <div class="nav-margin"><nuxt-link to="/blog">Blog</nuxt-link></div>
      </div>
    </header>
  
    <nav>
      <!-- Navigation -->
    </nav>
  
    <main>
      <!-- Main content -->
      <div class="flex-center">
        <div>
          <img width="30" src="~/assets/github192.png" />
          <img width="30" src="~/assets/hydra_chat192.jpg" />
        </div>
        <!-- pages -->
        <nuxt/>
      </div>
    </main>
  
    <aside>
      <!-- Sidebar / Ads -->
    </aside>
  
    <footer>
      <!-- Footer content -->
      <div v-bind:style="{ width: '20px' }"></div>
      <div class="flex-center">
        <div>Made with <img width="15" src="~/assets/vue_logo.svg" />ue and Nuxt.js (<img width="15" src="~/assets/nuxt_logo.svg" />)</div>
      </div>
    </footer>
  </div>
</template>

<script>
import AppLogo from "~/components/AppLogo.vue";

export default {
  components: {
    AppLogo
  }
};
</script>

<style lang="scss">
@media (min-width: 0px) {
  .grid-container {
    display: grid;
    grid-template-areas:
      "header header"
      "content content"
      "footer footer";
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 6fr 1fr;
    height: 98.5vh;
    background-color: #303030;
    color: white;
  }
}

@media (min-width: 800px) {
  .grid-container {
    grid-template-columns: 1fr 6fr 1fr;
    grid-template-rows: 1fr 6fr 1fr;
    grid-template-areas:
      "nav header  aside"
      "nav content aside"
      "nav content aside"
      "nav footer  aside";
    height: 98.5vh;
    background-color: #303030;
    color: white;
  }
}

header {
  grid-area: header;
  border: 1px solid red;
}

nav {
  grid-area: nav;
  margin-left: 0.5rem;
}

main {
  grid-area: content;
  border: 1px solid red;
}

aside {
  grid-area: aside;
  margin-right: 0.5rem;
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
  margin-left: "10px";
}

.flex-center {
  display: flex;
  justify-content: center;
  flex-direction: column;
  text-align: center;
}
</style>
