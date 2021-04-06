<template>
  <v-app>
    <v-main>
      <Stepper1/>
    </v-main>
  </v-app>
</template>

<script>
import Stepper1 from './components/Stepper1.vue'
export default {
  name: 'App',
  components: {
    Stepper1
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #989898;
  margin-top: 60px;
   background-color: #1e1e1e;
}

div{
  background-color: #1e1e1e;
}

.theme--light.v-stepper {
  background-color: #1e1e1e;
}

.theme--light.v-stepper .v-stepper__label {
    color: #ffb9b9;
}
.theme--light.v-stepper .v-stepper__step--complete .v-stepper__label{
color: #ffb9b9;
}

.theme--light.v-stepper .v-stepper__step:not(.v-stepper__step--active):not(.v-stepper__step--complete):not(.v-stepper__step--error) .v-stepper__step__step {
    background: rgb(48 48 48);
}

.v-application .primary {
  background-color: #ca4d4d  !important;
    box-shadow: 0 3px 1px -2px rgb(0 0 0 / 20%), 0 2px 2px 0 rgb(0 0 0 / 14%), 0 1px 5px 0 rgb(0 0 0 / 12%);
    border-color: #ffffff   !important ;
}

</style>
