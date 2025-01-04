<script setup>
import footerlinks from './data/footerlinks.json'
import {Hero, About, Projects, Services, Contact} from './views';
import { onMounted, onUnmounted } from 'vue';
onMounted(() => {
    const sections = document.querySelectorAll('.display');
    const navLinks = document.querySelectorAll('header nav a');

    const handleScroll = () => {
        const top = window.scrollY;

        sections.forEach((sec) => {
        const offset = sec.offsetTop - 150;
        const height = sec.offsetHeight;
        const id = sec.getAttribute('id');

        if (top >= offset && top < offset + height) {
            navLinks.forEach((link) => {
            link.classList.remove('active');
            });
            document
            .querySelector(`header nav a[href*="${id}"]`)
            .classList.add('active');
        }
        });
    };
    /* STICKY BEHAVIOR */
    //sticky nav test
    let lastScrollTop = 0;
    const navbar = document.getElementById("navbar");

    window.addEventListener("scroll", function() {
    const currentScroll = window.pageYOffset || document.documentElement.scrollTop;
    
    if (currentScroll > lastScrollTop) {
        // Scroll down - hide the navbar
        navbar.style.top = "-80px"; // Adjust this value depending on the height of your navbar
    } else {
        // Scroll up - show the navbar
        navbar.style.top = "0px";
    }
    
    lastScrollTop = currentScroll <= 0 ? 0 : currentScroll; // For Mobile or negative scrolling
    });
    /* BG-CHANGE BEHAVIOR */
    let nav = document.querySelector(".nav");
    window.onscroll = function() {
      if(document.documentElement.scrollTop > 20){
        nav.classList.add("new-bg");
      }else {
        nav.classList.remove("new-bg");
      }
    }
    /*  */
    window.addEventListener('scroll', handleScroll);

    // Clean up on component unmount
    onUnmounted(() => {
        window.removeEventListener('scroll', handleScroll);
    });
    });

</script>

<template>
<header class="nav" id="navbar" >
    <nav class="navbar" >
        <router-link class="active" to="#home">Home</router-link>
        <router-link to="#about">About</router-link>
        <router-link to="#projects">Projects</router-link>
        <router-link to="#services">Services</router-link>
        <router-link to="#contact">Contact</router-link>
    </nav>
</header>

<!-- SECTIONS -->
<Hero class="display" id="home" />
<About class="display" id="about" />
<Projects class="display" id="projects" />
<Services class="display" id="services" />
<Contact class="display" id="contact" />
<!-- SECTION END -->

<footer>
    <div class="container">
        <div class="links">
            <router-link class="active" to="#home">Home</router-link>
            <router-link to="#about">About</router-link>
            <router-link to="#projects">Projects</router-link>
            <router-link to="#services">Services</router-link>
            <router-link to="#contact">Contact</router-link>
        </div>
        <div class="socials">
            <a target="_blank" rel="noopener noreferrer" :href="footerlink.link" class="link" v-for="footerlink in footerlinks" :key="footerlink.id" v-html="footerlink.svg"></a>
        </div>
        <div class="site-info">
            <p>© 2025 Quantoxt, Inc. All rights reserved.</p>
        </div>
    </div>
</footer>

</template>

<style scoped>
.nav{
    .navbar{
    @apply flex items-center justify-center gap-3 font-medium text-base
    }
    .active{
    @apply text-white
    }
    a{
        @apply text-base sm:text-2xl
    }
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(20px);
    z-index: 100;
    @apply w-full text-gray-300 border border-slate-300 max-w-xs sm:max-w-md rounded-full h-11 sm:h-14 fixed right-0 left-0 mx-auto mt-6 sm:mt-10 shadow-lg flex items-center justify-center
}
.nav.new-bg{
    a{
        @apply text-slate-400
    }
    .active{
        color: white;
    }
    background:var(--gradient);
}
footer{
    .container{
        div{
            @apply w-full flex items-center justify-center flex-wrap font-medium gap-8
        }
        .links{
            a{
                @apply text-xl text-gray-300 hover:text-white
            }
            @apply gap-8 sm:gap-12
        }
        .socials{
            .link{
                @apply h-14 w-14 p-3 text-gray-300 hover:text-white
            }
        }
        .site-info{
            p{
                @apply text-gray-300
            }
        }
        @apply items-center justify-center
    }

    min-height: 30vh;
    background: #020344;
    @apply flex items-center justify-center 
}
</style>
