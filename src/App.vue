<template>
    <div>
        <h3>Hello World</h3>
        <h5>{{ name }}</h5>

        <HelloWorld :name="name" @pressed="pressed" class="green"/>
        <div v-if="pokemon">
            <img :src="pokemon.sprites.back_default" alt="">
        </div>
    </div>
</template>


<script setup>
    import { ref } from 'vue';
    import HelloWorld from './components/HelloWorld.vue';

    let name = 'kulotsystems';
    let pokemon = ref(null);

    async function pressed() {
        const info = await fetch('https://pokeapi.co/api/v2/pokemon/ditto');
        const json = await info.json();
        pokemon.value = json;
        console.log(pokemon.value);
    }
</script>


<style>
    #app {
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
