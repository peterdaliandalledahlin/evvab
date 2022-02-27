<template>
  <v-container id="suppliers">
    <v-row class="mt-3">
      <v-col v-for="supplier in suppliers" :key="supplier.id" cols="12" sm="4" lg="3">
        <v-card
          class="mx-auto"
          max-width="400"
        >
    <v-img
      class="white--text align-end"
      height="200px"
      :src="supplier.img"
    >
      <!-- <v-card-title>Det här blir en bra dag</v-card-title> -->
    </v-img>

    <v-card-subtitle class="pb-0">
      Number 10
    </v-card-subtitle>

    <v-card-text class="text--primary">
      <div>{{ supplier.title}}</div>

      <div>Whitsunday Island, Whitsunday Islands</div>
    </v-card-text>

    <v-card-actions>
      <v-btn
        color="#E74C13"
        text
        :href="supplier.link"
        target="_blank"
      >
        Till hemsidan
      </v-btn>

    </v-card-actions>
  </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      suppliers: [
                { id: 1, img: require('../assets/svedbergs.webp'), icon: 'mdi-domain', title: 'Svedbergs', link: 'https://www.svedbergs.se/'},
                { id: 2, img: require('../assets/noro.jpg'), icon: 'mdi-domain', title: 'Noro', link: 'https://www.noro.se/'},
                { id: 3, img: require('../assets/mora.webp'), icon: 'mdi-domain', title: 'Mora Armatur', link: 'https://www.moraarmatur.com/sv/'},
                { id: 4, img: require('../assets/grohe.jpg'), icon: 'mdi-domain', title: 'Grohe', link: 'https://www.grohe.sv/'},
                { id: 5, img: require('../assets/ifo.jpg'), icon: 'mdi-domain', title: 'Ifö', link: 'https://www.ifo.sv/'},
                { id: 6, img: require('../assets/nibe.png'), icon: 'mdi-domain', title: 'Nibe', link: 'https://www.nibe.eu/sv-se'},
                { id: 7, img: require('../assets/gustavsberg.png'), icon: 'mdi-domain', title: 'Gustavsberg', link: 'https://www.gustavsberg.com/se/'},
                { id: 8, img: require('../assets/ido.png'), icon: 'mdi-domain', title: 'Ido', link: 'https://www.ifo.se/ido/#gref'},
                { id: 9, img: require('../assets/ctc.png'), icon: 'mdi-domain', title: 'CTC', link: 'https://ctc.se/'},
                { id: 10, img: require('../assets/inr.png'), icon: 'mdi-domain', title: 'Inr', link: 'https://inr.se/'},

            ],
    }
  }
}
</script>

<style>

</style>