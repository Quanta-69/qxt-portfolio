<script setup>
import services from '../data/services.json'
</script>

<template>
    <section>
        <div class="container">
            <h2 class="sect-name">my services</h2>
            <h1 class="sect-intro">What I bring to the table</h1>
            <div class="cards">
                <div class="card" v-for="service in services" :key="service.id">
                    <div class="svg" v-html="service.svg "></div>
                    <h1>{{ service.title }}</h1>
                    <p>{{ service.description }}</p>
                </div>
            </div>
            <div class="outro">
                <h1>Not sure what you need? Let’s chat and find the perfect solution for you!</h1>
                <a href="https://wa.me/+2349134438269?text=Hi%20there%21%20I%27m%20messaging%20from%20your%20portfolio%20website%20and%20I%27m%20so%20excited%20to%20talk%20about%20a%20project%20with%20you.%20Can%27t%20wait%20to%20hear%20from%20you%21%20😊" target="_blank" rel="noopener noreferrer" ><button>chat me on whatsapp</button></a>
            </div>
        </div>
    </section>
</template>

<style scoped>
.svg{
    color:#28b8d5;
}
.card{
    h1{
        @apply font-medium text-2xl
    }
    p{
        @apply text-base text-slate-300 text-center sm:text-left
    }
    @apply max-w-md border-b border-b-slate-500 items-center sm:items-start
}
</style>
