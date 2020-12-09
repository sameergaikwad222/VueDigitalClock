<template>
  <v-container class="fill-height mx-auto d-flex justify-space-around">
    <!-- Year Card -->
    <v-hover v-slot="{ hover }" close-delay="200">
      <v-card
        v-if="showYear"
        :elevation="hover ? 16 : 2"
        :class="{ 'on-hover': hover }"
        v-ripple
        width="175px"
        height="175px"
        class="d-flex flex-column justify-center align-center"
      >
        <v-card-title>Year</v-card-title>
        <v-divider inset></v-divider>
        <v-card-text
          class="text-lg-h2 text-md-h3 text-sm-h5 text-xl-h2 text-h3 text-center"
        >
          {{ year }}
        </v-card-text>
      </v-card>
    </v-hover>
    <!-- Month Card -->
    <v-hover v-slot="{ hover }" close-delay="200">
      <v-card
        v-if="showMonth"
        :elevation="hover ? 16 : 2"
        :class="{ 'on-hover': hover }"
        v-ripple
        width="175px"
        height="175px"
        class="d-flex flex-column justify-center align-center"
      >
        <v-card-title>Month</v-card-title>
        <v-divider inset></v-divider>
        <v-card-text
          class="text-lg-h2 text-md-h3 text-sm-h5 text-xl-h2 text-h3 text-center"
        >
          {{ month }}
        </v-card-text>
      </v-card>
    </v-hover>
    <!-- Day Card -->
    <v-hover v-slot="{ hover }" close-delay="200">
      <v-card
        v-if="showDay"
        :elevation="hover ? 16 : 2"
        :class="{ 'on-hover': hover }"
        v-ripple
        width="175px"
        height="175px"
        class="d-flex flex-column justify-center align-center"
      >
        <v-card-title>Day</v-card-title>
        <v-divider inset></v-divider>
        <v-card-text
          class="text-lg-h2 text-md-h3 text-sm-h5 text-xl-h2 text-h3 text-center"
        >
          {{ day }}
        </v-card-text>
      </v-card>
    </v-hover>
    <!-- Hour Card -->
    <v-hover v-slot="{ hover }" close-delay="200">
      <v-card
        v-if="showHour"
        :elevation="hover ? 16 : 2"
        :class="{ 'on-hover': hover }"
        v-ripple
        width="175px"
        height="175px"
        class="d-flex flex-column justify-center align-center"
      >
        <v-card-title>Hour</v-card-title>
        <v-divider inset></v-divider>
        <v-card-text
          class="text-lg-h2 text-md-h3 text-sm-h5 text-xl-h2 text-h3 text-center"
        >
          {{ hour }}
        </v-card-text>
      </v-card>
    </v-hover>
    <!-- Minute Card -->
    <v-hover v-slot="{ hover }" close-delay="200">
      <v-card
        v-if="showMinute"
        :elevation="hover ? 16 : 2"
        :class="{ 'on-hover': hover }"
        v-ripple
        width="175px"
        height="175px"
        class="d-flex flex-column justify-center align-center"
      >
        <v-card-title>Minute</v-card-title>
        <v-divider inset></v-divider>
        <v-card-text
          class="text-lg-h2 text-md-h3 text-sm-h5 text-xl-h2 text-h3 text-center"
        >
          {{ minute }}
        </v-card-text>
      </v-card>
    </v-hover>
    <!-- Second Card -->
    <v-hover v-slot="{ hover }" close-delay="200">
      <v-card
        v-if="showSecond"
        :elevation="hover ? 16 : 2"
        :class="{ 'on-hover': hover }"
        v-ripple
        width="175px"
        height="175px"
        class="d-flex flex-column justify-center align-center"
      >
        <v-card-title>Second</v-card-title>
        <v-divider inset></v-divider>
        <v-card-text
          class="text-lg-h2 text-md-h3 text-sm-h5 text-xl-h2 text-h3 text-center"
        >
          {{ second }}
        </v-card-text>
      </v-card>
    </v-hover>
  </v-container>
</template>

<script>
import dayjs from "dayjs";
export default {
  props: {
    showYear: Boolean,
    showMonth: Boolean,
    showDay: Boolean,
    showHour: Boolean,
    showMinute: Boolean,
    showSecond: Boolean
  },
  data() {
    return {
      year: "2020",
      month: "Dec",
      day: "09",
      hour: "17",
      minute: "47",
      second: "00"
    };
  },
  methods: {
    timer() {
      var a = dayjs();
      this.year = a.format("YYYY");
      this.month = a.format("MMM");
      this.day = a.format("DD");
      this.hour = a.format("HH");
      this.minute = a.format("mm");
      this.second = a.format("ss");
    }
  },
  mounted() {
    this.timer();
    setInterval(this.timer, 1000);
  }
};
</script>

<style></style>
