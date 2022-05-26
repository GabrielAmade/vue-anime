<template>
  <div class="app">
    <header>
      <h1>The <strong>Anime</strong>Database</h1>
      <form class="search-box">
        <input
          type="search"
          class="search-field"
          placeholder="Search for an anime..."
          required
          v-model='search_query'
        />
      </form>
    </header>
    <main>
      <div class="cards">
        <CardAnime/>
      </div>
    </main>
  </div>
</template>

<script>
import {ref} from 'vue';
import CardAnime from "./components/CardAnime.vue"

export default {
  setup(){
      const search_query = ref("");
    return {
      search_query
    }
  },
  name: "App",
  components: {
    CardAnime,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;

  font-family: "Fira sans", sans-serif;
}

a {
  text-decoration: none;
}

header {
  padding-top: 50px;
  padding-bottom: 50px;

  h1 {
    color: #888;
    font-size: 42px;
    font-weight: 400;
    text-align: center;
    text-transform: uppercase;
    margin-bottom: 30px;

    strong {
      color: #313131;
    }
  }

  .search-box {
    display: flex;
    justify-content: center;
    padding-left: 30px;
    padding-right: 30px;

    .search-field {
      appearance: none;
      background: none;
      border: none;
      outline: none;

      background-color: #F3F3F3;

      display: block;
      width: 100%;
      max-width: 600px;
      padding: 15px;
      border-radius:8px;

      color: #313131;
      font-size:20px;

      transition: 0.4s;

      &::placeholder{
        color: #AAA;
      }
    }
  }
  main{
    max-width: 1200px;
    margin: 0 auto;
    padding-left: 30px;
    padding-right: 30px;

    .cards{
      display: flex;
      flex-wrap: wrap;
      margin: 0 -8px;
    }
  }
}
</style>
