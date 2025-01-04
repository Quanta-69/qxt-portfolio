<script setup>

import stats from '../data/stats.json'

</script>

<template>
    <section>
        <div class="container">
            <h2 class="sect-name">about me</h2>
            <h1 class="sect-intro">Building your ideas, one line at a time!</h1>
            <div class="content">
                <p class="txt" >Hey there! I'm a passionate developer who loves turning ideas into beautiful websites. With a focus on clean code and user-friendly design, I create sites that are not only functional but enjoyable to use.</p>
            </div>
            <div class="cards">
                <div class="card" v-for="stat in stats" :key="stat.id">
                    <h1>{{ stat.title }}</h1>
                    <p>{{ stat.description }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
section{
    @apply gap-16
}
.container{
    @apply w-full
}
.content{
    .txt{
        @apply text-2xl text-center sm:text-start
    }
}
.card{
    h1{
        @apply text-4xl font-semibold
    }
    p{
        @apply text-base
    }
    @apply items-center border-b border-gray-700 ps-4 max-w-80 sm:border-l sm:border-b-0 sm:items-start
}
</style>