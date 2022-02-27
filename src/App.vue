<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
    >
      <v-list-item three-line>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            EVVAB
          </v-list-item-title>
          <v-list-item-subtitle>
            Enköpings VVS & Värme - din leverantör för en säker vardag
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title @click="$vuetify.goTo(item.link, drawer = false,  {duration: 500, easing: 'easeInOutCubic'})">{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-list dense nav>
        <v-list-item
          link
          href="https://www.facebook.com/Altunagarden/"
          target="_blank"
          @click="drawer = false"
        >
          <v-list-item-icon>
            <v-icon>mdi-facebook</v-icon>
          </v-list-item-icon>
          <v-list-item-content> 
            <v-list-item-title>Facebook</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app elevate-on-scroll fade-img-on-scroll>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-spacer></v-spacer>
      
      <v-img class="mr-3" :src="require('./assets/logotype.png')" max-width="40" max-height="40"></v-img>
      <!-- <v-toolbar-title>EVVAB</v-toolbar-title> -->
    </v-app-bar>

    <v-main>
      <Jumbotron />
      <Current />
      <Heat />
      <Vvs />
      <About />
      <Contact />
      <Suppliers />
      <Rootdeduction />
      <Footer />
    </v-main>
    <Modal />
  </v-app>
</template>

<script>
import Jumbotron from './components/Jumbotron.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'
import Current from './components/Current.vue'
import Gallery from './components/Gallery.vue'
import Heat from './components/Heat.vue'
import Suppliers from './components/Suppliers.vue'
import Vvs from './components/Vvs.vue'
import Rootdeduction from './components/Rootdeduction.vue'
import Footer from './components/Footer.vue'
import Modal from './components/Modal.vue'

export default {
  name: 'App',

  components: {
  Jumbotron, About, Contact, Current, Gallery, Heat, Suppliers, Vvs, Rootdeduction, Footer, Modal
  },

  data: () => ({
    drawer: null,
    items: [
          { id: 1, title: 'Hem', icon: 'mdi-home', link: '#home' },
          { id: 2, title: 'Kontakt', icon: 'mdi-account-box', link: '#contact' },
          { id: 3, title: 'Leverantörer', icon: 'mdi-hammer-screwdriver', link: '#suppliers' },
          { id: 4, title: 'Aktuellt', icon: 'mdi-bell-ring', link: '#current'  },
          { id: 5, title: 'Om EVVAB', icon: 'mdi-information', link: '#about' },
          { id: 6, title: 'VVS ', icon: 'mdi-pipe-leak', link: '#vvs' },
          { id: 7, title: 'Värme', icon: 'mdi-radiator', link: '#heat' },
          { id: 9, title: 'Galleri', icon: 'mdi-view-gallery', link: '#gallery' },
          { id: 9, title: 'ROT-avdrag', icon: 'mdi-square-root', link: '#rootreduction' },
        ],
  }),
};
</script>
