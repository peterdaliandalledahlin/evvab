<template>
  <v-container id="current">
      <h1>här kommer information om aktuellt visas</h1>
  </v-container>
</template>

<script>
export default {
  name: 'current',

}
</script>

<style scoped>
/* #current {
  background-color: #a40606;
  background-image: linear-gradient(315deg, #a40606 0%, #E74C13 74%);

} */
h1 {
  /* background-color: #ff4e00;
background-image: linear-gradient(315deg, #ff4e00 0%, #ec9f05 74%); */
background-color: #a40606;
background-image: linear-gradient(315deg, #a40606 0%, #E74C13 74%);


  /* background-color: #a40606;
  background-image: linear-gradient(315deg, #a40606 0%, #E74C13 74%);*/
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent; 
  font-size: 3rem;
 }
</style>