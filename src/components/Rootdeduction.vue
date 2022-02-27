<template>
  <v-container id="rootreduction">
      <p>Rotavdrag Sedan den 8 december 2008 är ROT-avdraget återinfört. Villaägare och bostadsrättsinnehavare får göra ett skatteavdrag med 30 % på belopp upp till maximalt 100 000 kronor när man anlitar en hantverkare för renovering, ombyggnad eller tillbyggnad. Avdraget gäller enbart arbets-kostnaden.  Läs mer om ROT-avdraget på nedanstående länk.</p>
      <v-card
        class="mx-auto"
    >
        <v-list>
        <v-list-item
            href="https://skatteverket.se/"
            target="_blank"
            rel="noopener"
        >
            <v-list-item-icon>
            <v-icon
                
            >
                mdi-square-root
            </v-icon>
            </v-list-item-icon>

            <v-list-item-content>
            <v-list-item-title>Länk till Skatteverkets hemsida</v-list-item-title>
            </v-list-item-content>

            <v-list-item-avatar>
                <v-img :src="require('../assets/skatteverket.webp')"></v-img>
            </v-list-item-avatar>
        </v-list-item>
        </v-list>
    </v-card>
  </v-container>
</template>

<script>
export default {

}
</script>

<style>

</style>