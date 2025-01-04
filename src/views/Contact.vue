<script setup>
import contacts from '../data/contacts.json'
</script>

<template>
    <section>
        <div class="container">
            <h2 class="sect-name">get in touch</h2>
            <h1 class="sect-intro">Have a project in mind or just want to chat? I’d love to hear from you!</h1>
            <div class="cards">
                <div class="card" v-for="contact in contacts" :key="contact.id">
                    <div class="svg" v-html="contact.svg"></div>
                    <h1>{{ contact.title }}</h1>
                    <p>{{ contact.description }}</p>
                    <a :href="contact.link" target="_blank" rel="noopener noreferrer">Explore<span><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M10 6V8H5V19H16V14H18V20C18 20.5523 17.5523 21 17 21H4C3.44772 21 3 20.5523 3 20V7C3 6.44772 3.44772 6 4 6H10ZM21 3V12L17.206 8.207L11.2071 14.2071L9.79289 12.7929L15.792 6.793L12 3H21Z"></path></svg></span></a>
                </div>
            </div>
            <div class="outro">
                <h1>Ready to start? Let’s chat now!</h1>
                <a href="https://wa.me/+2349234438269?text=Hi%20there%21%20I%27m%20messaging%20from%20your%20portfolio%20website%20and%20I%27m%20so%20excited%20to%20talk%20about%20a%20project%20with%20you.%20Can%27t%20wait%20to%20hear%20from%20you%21%20😊" target="_blank" rel="noopener noreferrer" ><button>leave me a message</button></a>
            </div>
        </div>
    </section>
</template>

<style scoped>
.svg{
    color:#020344;
}
.card{
    h1{
        @apply text-xl font-medium
    }
    p{
        @apply text-slate-300 text-base
    }
    a{
        span{
            @apply p-1 h-7 w-7
        }
        @apply underline font-medium inline-flex justify-center items-center text-base
    }
    background: rgba(255, 255, 255, 0.122);
    backdrop-filter: blur(10px);
    @apply max-w-md items-center rounded-xl sm:max-w-80 sm:items-start gap-1
}
</style>