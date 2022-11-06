<template>
  <div class="container">
    <PokemonList v-on:showPokemonDetailEmit="update"/>
    <PokemonDetail :urlpokemon="envoi" v-if="verif"  v-on:closed="verif=false"/>
  </div>
</template>

<script>
import PokemonDetail from "../components/PokemonDetail.vue";
import PokemonList from "../components/PokemonList.vue";
//import PokemonSearch from "../components/PokemonSearch.vue";

export default {
  name: "Pokedex",
  data(){
    return{
      verif:false,
      envoi: "JeanMich",
    }  
  },
  components: {
    PokemonDetail,
    PokemonList,
    //PokemonSearch,
  },
  methods: {
    update: function(pok){
      this.verif=true;
      this.envoi=pok;
    }
  }
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 10px;
  width: calc(100% - 20px);
  min-height: calc(100vh - 20px);
  //background: radial-gradient(#ffbf0b, #e20000);

  font-family: "Acme", arial;
  font-size: 1rem;
  font-weight: normal;
}

h1 {
  color: #efefef;
}
</style>