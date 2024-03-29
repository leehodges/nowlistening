<template>
  <div :class="rootClass">
    <Header :isAuth="isAuth"/>
    <section class="content">
      <nuxt/>
    </section>
    <Footer/>
    <nuxt-link v-if="isAuth" class="area-close" aria-hidden="true" to="/" name="index"></nuxt-link>
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: { Header, Footer },
  titleShort: 'Coding to',
  authorName: 'Lee',
  emojiIcon: ' 🎧 ',
  computed: {
    isAuth() {
      return this.$route.name === 'auth'
    },
    ariaCurrent() {
      return this.isAuth ? 'page' : false
    },
    rootClass() {
      return this.isAuth ? 'auth base' : 'base'
    }
  },
  head() {
    return {
      title: `${this.$options.authorName} ${
        this.$options.titleShort
      } Spotify`,
      link: [
        {
          rel: 'stylesheet',
          href: 'https://fonts.googleapis.com/css?family=Monoton|Oswald|Orbitron|Creepster'
        }
      ]
    }
  }
}
</script>

<style>
:root {
  --colorGray: #333642;
  --colorBlue: rgba(118, 120, 224, 0.5);
  --colorBrightBlue: rgb(0, 112, 255);
}
html {
  background: #000000;
}
body {
  padding: 0;
  margin: 0;
  color: white;
  font-family: 'orbitron', monospace;
  color: #F8F8FF;
}
.base {
  background-size: cover;
  background-image: linear-gradient(to top, var(--colorGray), #000000);
  display: grid;
  grid-template-rows: auto 1fr auto;
  height: 100vh;
  overflow-x: hidden;
}
a {
  color: white;
  text-decoration: none;
  display: inline-block;
  position: relative;
}
a:not(.area-close):after,
a:not(.area-close):before {
  content: '';
  position: absolute;
  left: 0;
  right: 0;
  height: 1em;
  z-index: -1;
  mix-blend-mode: color-burn;
}
a:after {
  bottom: 2px;
  background: var(--colorBlue);
  z-index: -1;
  transform: rotate(-3deg);
}
a:before {
  background: rgba(118, 120, 224, 0.4);
  transform: rotate(2deg);
}
.auth header,
.auth footer {
  filter: blur(20px);
}

.content {
  transform: translateY(10em);
  height: 0;
}
.auth .content {
  transform: translateY(0) !important;
}
.nuxt-progress {
  opacity: 0.3;
  height: 2px;
  bottom: 0;
  top: auto;
}

a.area-close {
  display: block;
  height: 100vh;
  width: 100vw;
  position: fixed;
  top: 0;
  z-index: 0;
  cursor: default;
}
@media (min-width: 1401px) {
  .content {
    transform: translateY(17em);
  }
}
@media (max-width: 1400px) {
  .content {
    transform: translateY(17em);
  }

}

@media (max-width: 1200px) {
  .content {
    transform: translateY(17em);
  }
}

@media (max-width: 1100px) {
  h1 {
    font-size: 8em !important;
    margin-top:10rem;
  }
  .content {
    transform: translateY(17em);
  }
}
@media (max-width: 800px) {
  h1 {
    font-size: 7em !important;
  }
  .content {
    transform: translateY(17em);
  }
}
@media (max-width: 600px) {
  h1 {
    font-size: 5em !important;
  }
  h2 {
    font-size: 2em !important;
    line-height: 1.2em;
  }

  .content {
    transform: translateY(3em);
  }
}
@media (max-width: 500px) {
  h1 {
    font-size: 3em !important;
  }

  .content {
    transform: translateY(3em);
  }

}
@media (max-width: 280px) {
  h1 {
    font-size: 2em !important;
    margin-left: -2.3rem;
    margin-top:3rem;
  }

  .content {
    transform: translate3d(-1.5rem, 3rem, 0rem);
  }
  footer {
    transform: translate3d(-1.2rem, 0rem, 0rem);

  }

}
</style>
