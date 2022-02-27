<template id="#pokeApi">

  <div class="">
    <img src="" alt="">
  </div>

  <div>
    <h1>
      PokeGuía
    </h1>
  </div>

  <form @submit.prevent="buscarPokemon(name)">
    <label>Nombre</label>
    <input type="text" v-model="name">
    <button type="submite">Buscar</button>
  </form>

  <PaintPokemon 

  :poke="arrPoke"

  :img="img"

  />

</template>

<script>
import PaintPokemon from './PaintPokemon.vue'

export default {
  name: 'PokeApi',
  components: {
    PaintPokemon
  },
  data(){
    return {
      url: "https://pokeapi.co/api/v2/pokemon/",
      name: "",
      arrPoke: [],
    }
  },
  created() {
    this.buscarPokemon("pikachu");
  },

  computed: {
      img(){
          return this.arrPoke.sprites.other['official-artwork'].front_default;
      }
  },

  methods:{
    async buscarPokemon(value){

      try {

        let res = await fetch(`https://pokeapi.co/api/v2/pokemon/${value}`)
        let data = await res.json()
        
        this.arrPoke = data

        console.log(this.arrPoke)

      }catch(err){
        console.log(err)
      }

    },
}};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>