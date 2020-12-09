<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <v-container>
        <v-switch v-model="clear" label="Clear All" color="red"></v-switch>
        <v-switch v-model="set" label="Set All" color="green"></v-switch>
      </v-container>
      <v-divider inset></v-divider>
      <v-container class="d-flex flex-column justify-space-around">
        <v-switch v-model="showYear" color="teal" label="Year"></v-switch>
        <v-switch v-model="showMonth" color="red" label="Month"></v-switch>
        <v-switch v-model="showDay" color="purple" label="Day"></v-switch>
        <v-switch v-model="showHour" color="green" label="Hour"></v-switch>
        <v-switch v-model="showMinute" color="pink" label="Minute"></v-switch>
        <v-switch v-model="showSecond" color="blue" label="Second"></v-switch>
      </v-container>
    </v-navigation-drawer>

    <v-app-bar
      app
      color="purple"
      extended
      src="https://picsum.photos/1920/1080?random"
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(19,84,122,.5), rgba(128,208,199,.8)"
        ></v-img>
      </template>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Digital Clock</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <timer
        class="mx-auto"
        :showYear="showYear"
        :showMonth="showMonth"
        :showDay="showDay"
        :showHour="showHour"
        :showMinute="showMinute"
        :showSecond="showSecond"
      />
    </v-main>
    <v-btn
      class="mx-2"
      fab
      dark
      large
      color="purple"
      id="GitFloat"
      @click="routeToMySite()"
    >
      <v-icon dark>
        mdi-github
      </v-icon>
    </v-btn>
  </v-app>
</template>

<script>
import timer from "./components/timer";
export default {
  name: "App",

  components: {
    timer
  },

  data: () => ({
    drawer: null,
    clear: false,
    set: false,
    showYear: false,
    showMonth: false,
    showDay: false,
    showHour: false,
    showMinute: false,
    showSecond: false
  }),

  methods: {
    clearAll() {
      this.showYear = false;
      this.showMonth = false;
      this.showDay = false;
      this.showHour = false;
      this.showMinute = false;
      this.showSecond = false;
    },
    setAll() {
      this.showYear = true;
      this.showMonth = true;
      this.showDay = true;
      this.showHour = true;
      this.showMinute = true;
      this.showSecond = true;
    },
    routeToMySite() {
      window.open(
        "https://github.com/sameergaikwad222/VueDigitalClock.git",
        "_blank"
      );
    }
  },
  watch: {
    clear(value) {
      if (value) {
        this.clearAll();
        this.set = false;
      }
    },
    set(value) {
      if (value) {
        this.setAll();
        this.clear = false;
      }
    }
  }
};
</script>

<style scoped>
body {
  position: relative;
}
#GitFloat {
  position: absolute;
  bottom: 2.7%;
  right: 2%;
}
</style>
