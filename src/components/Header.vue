<template>
    ini header
    <pre>state : {{counter}}</pre>
    <pre>getters : {{getCount}}</pre>
    <pre>double count : {{doubleCount}}</pre>
    <pre>divided count : {{divededByTwo}}</pre>
    <pre>pokemon : {{pokemon}}</pre>
</template>

<script setup>
import {computed} from 'vue'
import {useCounterStore} from '../store/counter'
import {usePokemonStore} from '../store/pokemon'

const counterStore = useCounterStore()
const PokemonStore = usePokemonStore()

const counter = computed(() => counterStore.count)
const getCount = computed(() => counterStore.getCount)
const doubleCount = computed(() => counterStore.doubleCount)
const divededByTwo = computed(() => counterStore.dividedBy(2))

const pokemon = computed(() => PokemonStore.pokemonDetails)

counterStore.$subscribe((mutation, state) => {
console.log(mutation, state)
});
</script>
