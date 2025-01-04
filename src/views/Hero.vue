<script setup>
import { defineProps } from 'vue';

defineProps({
    name:{
    type: String,
    default:'Godstime'
    }
})
</script>

<template>
    <section>
        <div class="wrapper">
            <div class="txt">
                <h1>Hi There, I’m {{ name }}! <br> Let’s build something amazing. Together.</h1>
                <h2>I create modern, beautiful, and user-friendly websites that make ideas come to life. Let’s turn your vision into reality!</h2>
            </div>
            <div class="btn-wrap">
                <router-link to="#projects">
                    <button>see my works</button>
                </router-link>
                <router-link to="#contact">
                    <button>let's collaborate</button>
                </router-link>
            </div>
        </div>
    </section>
</template>

<style scoped>
section{
    min-height: 90vh;
}
.txt{

    h1{
        @apply text-5xl font-semibold text-center text-white my-8 sm:text-7xl
    }
    h2{
        @apply text-xl font-medium text-center text-slate-100 my-8 sm:text-3xl
    }
    @apply w-full max-w-screen-xl
}
.btn-wrap{

    button{
        background:linear-gradient(-40deg, #020344, #28b8d5);
        @apply  text-white font-medium text-xl
    }
}

</style>