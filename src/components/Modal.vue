<template>
  <v-dialog
      v-model="dialog"
      scrollable
      max-width="300px"
    >
      <!-- <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="primary"
          dark
          v-bind="attrs"
          v-on="on"
        >
          Open Dialog
        </v-btn>
      </template> -->
      <v-card>
        <v-card-title class="text-h6 text-center">EVVAB</v-card-title>
        
        <v-divider class="my-3"></v-divider>
        
        <v-card-text class="text-center">
          Månadens Erbjudande!
          <v-btn small @click="$vuetify.goTo('#membership', dialog = false,  {duration: 500, easing: 'easeInOutCubic'})" max-width="200" class="my-3">Jag vill veta mer...</v-btn>
          

          
          <v-divider class="my-3"></v-divider>
          
          Här kan man också informera om något spännande.
<br />
          <v-btn small @click="$vuetify.goTo('#contact', dialog = false,  {duration: 500, easing: 'easeInOutCubic'})" max-width="200" class="mt-3">Till kontaktsidan</v-btn>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions class="justify-end">
          <v-btn
            color="#a55c1b"
            text
            @click="dialog = false"
          >
            Stäng
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
</template>

<script>
export default {
  name: 'modal',
    data() {
        return {
            dialog: true,
        }
    }
}
</script>

<style>

</style>