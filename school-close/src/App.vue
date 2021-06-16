<template>
  <v-app>
    <v-main>
      <v-container>
        <v-row>
          <v-col>
            <Bord/>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Bord from './components/Bord'

export default {
  name: 'App',

  components: {
    // HelloWorld
    Bord
  }
}
</script>
