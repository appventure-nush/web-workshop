<template>
  <v-container fluid>

    <h1>
      Jobs
    </h1>

    <v-autocomplete
      label="Search your jobs"
      class="my-5"
      filled
    >

    </v-autocomplete>

      <v-row
        justify="center"
        align="center"
      >
      </v-row>

    <v-layout row wrap class="mx-5">
      <v-flex
        shrink
        align-self-start
        v-for="job in jobs"
        :key="job.id">

        <Job
        :job="job">

        </Job>
      </v-flex>
    </v-layout>

  </v-container>
</template>

<script lang="ts">
import Vue from "vue";
import Job from "@/types/Job.vue";

export default Vue.extend({
  name: "Main",
  components: {Job},
  data: function () {
    return {
      jobs: [{
        title: "Lunar Eclipse",
        id: "kdjfkljlkj",
        date: new Date("2022-04-13T01:02:03.000+08:00"),
        description: "Lorem ipsum",
        groups: ["personal","friends"]
      }, {
        title: "Lunar Eclipse",
        id: "kjkdjldjslj",
        date: new Date("2022-04-13T01:02:03.000+08:00"),
        description: "Lorem ipsum",
        groups: ["personal","friends"]
      }],
    };
  },
});
</script>
