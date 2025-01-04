<script setup>
import projects from '../data/projects.json'
</script>

<template>
    <section class="overlay">
        <div class="container">
            <h2 class="sect-name">my proud creations</h2>
            <h1 class="sect-intro">Some of my favorite projects — crafted with care and lots of code magic!</h1>
            <div class="cards">
                <div class="card" v-for="project in projects" :key="project.id">
                    <div class="image">
                        <img :src="project.img" alt="Img">
                    </div>
                    <div class="content">
                        <h1>{{ project.title }}</h1>
                        <p>{{ project.description }}</p>
                        <div class="link">
                            <span><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M17.6567 14.8284L16.2425 13.4142L17.6567 12C19.2188 10.4379 19.2188 7.90524 17.6567 6.34314C16.0946 4.78105 13.5619 4.78105 11.9998 6.34314L10.5856 7.75736L9.17139 6.34314L10.5856 4.92893C12.9287 2.58578 16.7277 2.58578 19.0709 4.92893C21.414 7.27208 21.414 11.0711 19.0709 13.4142L17.6567 14.8284ZM14.8282 17.6569L13.414 19.0711C11.0709 21.4142 7.27189 21.4142 4.92875 19.0711C2.5856 16.7279 2.5856 12.9289 4.92875 10.5858L6.34296 9.17157L7.75717 10.5858L6.34296 12C4.78086 13.5621 4.78086 16.0948 6.34296 17.6569C7.90506 19.2189 10.4377 19.2189 11.9998 17.6569L13.414 16.2426L14.8282 17.6569ZM14.8282 7.75736L16.2425 9.17157L9.17139 16.2426L7.75717 14.8284L14.8282 7.75736Z"></path></svg></span>
                            <a target="_blank" rel="noopener noreferrer" :href="project.link">live preview</a>
                        </div>
                    </div>
                </div>
            </div>
            <div class="outro">
                <h1>Have a project in mind? Let's make it happen!</h1>
                <a href="https://wa.me/+2349234438269?text=Hi%20there%21%20I%27m%20messaging%20from%20your%20portfolio%20website%20and%20I%27m%20so%20excited%20to%20talk%20about%20a%20project%20with%20you.%20Can%27t%20wait%20to%20hear%20from%20you%21%20😊" target="_blank" rel="noopener noreferrer" ><button>get your own project</button></a>
            </div>
        </div>
    </section>
</template>

<style scoped>
section{
    background: url(../bg.jpg) center/cover fixed;
}
.card{
    .image{
        img{
            @apply h-full w-full rounded-xl object-scale-down
        }
        @apply w-full m-0  h-full max-w-full rounded-xl
    }
    .content{
        background: linear-gradient(to left, rgba(255, 255, 255, 0.163), #28b8d560);
        -webkit-backdrop-filter: blur(10px);
        backdrop-filter: blur(10px);
        @apply px-4 py-2 w-full rounded-xl
    }
    h1{
        @apply font-medium text-2xl rounded-xl
    }
    p{
        @apply text-base text-slate-300 rounded-xl
    }
    .link{
        span{
            @apply h-10 w-10 p-2
        }
        a{
            @apply underline
        }
        @apply inline-flex items-center w-full
    }
    background: rgba(255, 255, 255, 0.063);
    backdrop-filter: blur(10px);
    transition: .3s;
    @apply max-w-md rounded-xl border border-slate-500  relative
}
.card:hover{
    transform: translateY(-10px);
}
</style>