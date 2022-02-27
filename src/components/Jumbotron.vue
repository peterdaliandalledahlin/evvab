<template>
  <v-parallax
      ref="home"
      dark
      :src="require('@/assets/jumbotron-bg.jpg')"
      id="home"
    >
      <v-row
        align="center"
        justify="center"
      >
        <v-col
          class="text-center"
          cols="12"
        >
          <h1 id="evvab-color" :class="{'text-h1 font-weight-black mb-4' : $vuetify.breakpoint.lg, 'text-h2 mb-4' : $vuetify.breakpoint.md, 'text-h3 mb-4' : $vuetify.breakpoint.sm, 'text-h2 mb-4' : $vuetify.breakpoint.xs}">
            <span class="evvab">E<span id="letter-v">{{letterV}}</span><span id="vab">{{vab}}</span></span>
          </h1>
          <h2 :class="{'text-h5 mb-4' : $vuetify.breakpoint.lg, 'text-h3 mb-4' : $vuetify.breakpoint.md, 'text-h4 mb-4' : $vuetify.breakpoint.sm,  'text-h6 mb-5' : $vuetify.breakpoint.xs}">
            Enköpings VVS & Värme - Din leverantör för en säker vardag
          </h2>
          <p>EVVAB är ett serviceföretag inom VVS med hel- och kvällsjour. Vi utför allt inom VVS, från reparationer av kranar, avlopp, beredare, WC etc till nyinstallationer av VVS, värme och golvvärme.</p>
          <!-- <v-container class="mx-auto">
              <v-row>
                <v-col xs="12" md="6">
                    <v-btn @click="$vuetify.goTo('#book',  {duration: 500, easing: 'easeInOutCubic'})" color="black" max-width="200" id="opacity-btn-1" class="mb-2">
              Kontakt
            </v-btn>
            <v-btn @click="$vuetify.goTo('#events', {duration: 500, easing: 'easeInOutCubic'})" color="black" max-width="200" id="opacity-btn-1">
              Aktuellt
            </v-btn>
                </v-col>
            </v-row>
          </v-container> -->
        </v-col>
      </v-row>
    </v-parallax>
</template>

<script>
  export default {
    name: 'home',
    data: () => ({
        letterV: 'V',
        vab: 'VAB'
    }),
    methods: {
        testfunction(){
            this.letterV = ''   
        }
    },
    mounted(){
        setTimeout(() => {this.testfunction()}, 3000);
        
    }
  }
</script>

<style scoped>
/* @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@700&display=swap'); */
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@700&family=Work+Sans:wght@700&display=swap');
#opacity-btn-1, #opacity-btn-2 {
  background-color: rgba(165,92,27, .7) !important;
}
.outline {
  -webkit-text-stroke: 1px black;
}
.evvab {
    /* font-family: 'Open Sans', sans-serif; */
    font-family: 'Work Sans', sans-serif;
    color: #E74C13 !important;
    animation: animateletterspacing 2s ease-in forwards;
     display: inline-block;
            transform: scale(1, 1.5);
  -webkit-transform: scale(1, 1.5); /* Safari and Chrome */
  -moz-transform: scale(1, 1.5); /* Firefox */
  -ms-transform: scale(1, 1.5); /* IE 9+ */
  -o-transform: scale(1, 1.5); /* Opera */
}

@keyframes animateletterspacing {
    0% {
        letter-spacing: 1em;
    }

    20% {
        letter-spacing: .5em;
    }

    100% {
        letter-spacing: -.23em;
    }
}
#letter-v {  
  animation-duration: 3s;
  animation-fill-mode: both;
  animation-iteration-count: 1;
}
#letter-v {
  -webkit-animation-name: remove-v;
  animation-name: remove-v;
}
@keyframes remove-v {
  0% {
    opacity: 1;
  }


  100% {
    opacity: .2;
    display: none;
  }
}
#vab {  
  animation-duration: 3s;
  animation-fill-mode: both;
  animation-iteration-count: 1;
}
#vab {
  -webkit-animation-name: move-vab-left;
  animation-name: move-vab-left;
}
@keyframes move-vab-left {
  0% {
    transform: translateX(0px);
  }


  100% {
    transform: translateX(-100px);
  }
}
</style>