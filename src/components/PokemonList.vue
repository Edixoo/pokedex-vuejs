<template>
  <div class="list"></div>
</template>

<script>
import axios from 'axios';

export default {
  name: "app",
  data() {
    return{
      name: "Paul",
      pokemon: null,
      img_pokemon: null
    };
  },
  mounted () {
    axios
      .get("https://pokeapi.co/api/v2/pokemon")
      .then(response => (this.pokemon = response.results));
    axios
      .get("https://img.pokemondb.net/sprites/bank/normal/")
      .then(response =>(this.img_pokemon = response))
  }
};
</script>

<style lang="scss" scoped>

.list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  grid-gap: 10px;
  width: 100%;
  max-width: 510px;
}

article {
  height: 150px;
  background-color: #efefef;
  text-align: center;
  text-transform: capitalize;
  border-radius: 5px;
  cursor: pointer;
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2), 0 10px 10px rgba(0, 0, 0, 0.2);
}

h3 {
  margin: 0;
}

#scroll-trigger {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 150px;
  font-size: 2rem;
  color: #efefef;
}

img {
  width: 96px;
  height: 96px;
}

</style>

