<template>
    ini footer
    <br>
    <button @click="increment">increment +</button>
    <button @click="decrement">decrement -</button>
    <button @click="reset">reset</button>

    <button @click="incrementWithAction">increment with action</button>
    <button @click="decrementWithAction">decrement with action</button>
    <button @click="incrementByWithAction(5)">incrementBy with action by 5</button>
    <hr>
    <button @click="fetchPokemon('ditto')">fetch ditto</button>
    <button @click="resetPokemon">reset pokemon</button>
</template>

<script setup>
import {useCounterStore} from '../store/counter'
import {usePokemonStore} from '../store/pokemon'

const counter = useCounterStore();
const pokemon = usePokemonStore();

const increment = () => {
    counter.$patch((state) => 
    {
        state.count++
    })
}
const decrement = () => {
    counter.$patch((state) => 
    {
        state.count--
    })
}
const reset = () => {
    counter.$reset() 
}

const incrementWithAction = () => {
    counter.increment()
}
const decrementWithAction = () => {
    counter.decrement()
}
const incrementByWithAction = (amount) => {
    counter.incrementBy(amount)
}
const fetchPokemon = (name) => {
    pokemon.getPokemonDetails(name)
}
const resetPokemon = () => {
    pokemon.$reset()
}

</script>
