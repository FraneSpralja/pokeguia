<template>
    <div class="card">
        <img :src="img" alt="" class="card_top">
        <div class="card__body">

            <div class="body__top">
                <h3 class="card_title_one">
                    Movimientos
                </h3>
                <ul class="move__list">
                    <li class="move__item" v-for="item in poke.moves" :key="item">
                        {{item.move.name}}
                    </li>
                </ul>
            </div>

            <div class="body__bottom">
                <h3 class="card_title_one">
                    Habilidades
                </h3>
                <ul class="move__list">
                    <li class="move__item" v-for="item in poke.abilities" :key="item">
                        {{item.ability.name}}
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PaintPokemon',
    props: {
        poke: Array,
        img: String,
    },
}
</script>

<style>

</style>