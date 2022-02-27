<template>
  <v-container fluid class="pa-0">
      
    <v-footer class="pa-0">
      <v-card
        flat
        tile
        width="100%"
        class="text-center"
      >
        <v-card-text>
          <v-btn
            v-for="item in icons"
            :key="item.id"
            class="mx-4"
            icon
          >
            <v-icon size="24px" @click="$vuetify.goTo(item.link,  {duration: 500, easing: 'easeInOutCubic'})">
              {{ item.icon }}
            </v-icon>
          </v-btn>
           <v-btn
                icon
                href="tel:+46728585757"
          >
                <v-icon size="24px">
                mdi-cellphone
                </v-icon>
          </v-btn>
          <v-btn
                icon
                href="mailto:info@evvab.se"
          >
                <v-icon size="24px">
                mdi-at
                </v-icon>
          </v-btn>
        </v-card-text>

        
         
    

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>&copy; EVVAB<br /> <a href="tel:+46728585757">072-858 57 57</a> <a href="mailto:info@evvab.se">info@evvab.se</a> Mångatan 21 • 749 44 Enköping</strong>
        </v-card-text>
        <v-card-text>
            <v-chip
                class="ma-2"
                color="white"
                outlined
            >
                <v-icon left>
                    mdi-wrench
                </v-icon>
                made by peterdaliandalledahlin@gmail.com
            </v-chip>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-container>
</template>

<script>
export default {
    data: () => ({
      icons: [
        {id: 1, link: '#home', icon: 'mdi-home'},
        {id: 2, link: '#contact', icon: 'mdi-account-box'},
        {id: 4, link: '#current', icon: 'mdi-bell-ring'},
      ],
    }),
    computed: {

    },
}
</script>

<style scoped>
.v-card__text.white--text {
    padding: 0 !important;
}
/* .gradient::before {
  content: '';
	position: absolute;
	top: 0;
	right: 0;
	bottom: 0;
	left: 0;
	background-image: linear-gradient(to bottom right,#000000,#a55c1b);
	opacity: .6; 
} */
</style>