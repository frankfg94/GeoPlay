<!-- Landing page, allow the user to go to the login page and read informations about GeoPlay -->
<template>
  <v-container>
    <div
      class="px-0"
      align="center"
    >
      <!-- Background image-->
      <v-parallax
        height="320"
        src="https://cdn.pixabay.com/photo/2012/01/09/09/59/earth-11595_1280.jpg"
      >
        <div class="font-weight-regular main-title">
          Geo Play
        </div>
        <br>
        <div class="blue-text-shadow">
          Free online geography guessing game
        </div>
        <br>
        <div class="text-xs-center">
          <v-btn
            to="/homepage"
            class="no-border"
            color="primary"
            max-width="200px"
          >
            Start playing
          </v-btn>
        </div>
      </v-parallax>
      <v-row
        no-gutters
        align-content="stretch"
      >
        <v-col
          cols="12"
          align="center"
        >
          <v-row class="left ma-12">
            <div class="font-weight-medium subtitle">
              About
            </div>
            <div class="text-left">
              Play an exceedingly fun game where you must guess a location on 3
              different maps. Each game consists of questions that correspond to
              a location.
            </div>
          </v-row>
          <v-row class="left ma-12">
            <div class="font-weight-medium subtitle">
              Playing
            </div>
            <div class="text-left">
              At each question, you have a limited time to determine the
              location. You gain a point for each location guessed succesfully.
              The person with the best score will be the geo winner!
            </div>
          </v-row>
          <!-- Feature List -->
          <v-btn
            elevation="0"
            color="rgb(0, 0, 0, 0)"
            class="outlined ma-0 no-border"
            @click="$vuetify.goTo('#features')"
          >
            More
          </v-btn>
          <v-divider
            id="features"
            class="ma-12"
          />
          <Features />
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>
<script>
export default {
  layout: 'blank'
}
</script>

<style scoped>
.blue-text-shadow {
  text-shadow: 1px 1px 20px blue;
}
.main-title {
  font-size: 2.2em;
}
.subtitle {
  font-size: 1.3em;
}
.no-border {
  border-radius: 0px;
}
</style>
