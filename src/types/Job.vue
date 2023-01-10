<template>
  <v-card
    class="mx-5 px-5"
    max-width="500"

  >
    <v-list-item two-line>
      <v-list-item-content>
        <v-list-item-title class="text-h5">
          {{job.title}}
        </v-list-item-title>
      </v-list-item-content>
    </v-list-item>

    <v-card-text
      class="text-h4"
      cols="10"
    >
          {{ this.formatDate(job.date)}}
    </v-card-text>

    <v-card-text>
      {{job.description.slice(0,30)}}
    </v-card-text>



    <v-divider></v-divider>

    <v-card-actions>
      <v-btn text>
        Mailing List
      </v-btn>
    </v-card-actions>
    <v-card-text>
      <v-chip-group
        active-class="deep-purple accent-4 white--text"
        column
      >
        <v-chip
          v-for="group in job.groups"
          :key="group"
        >
          {{group}}
        </v-chip>
      </v-chip-group>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">

import {Job} from "@/types/Job";

export default {
  props: {
    job: Job
  },
  name: "Job",
  methods: {
    formatDate: function(date: Date) : string {
      const tmp = date.toDateString().split(" ");
      return tmp[0] + ", " + tmp[1] + " " + tmp[2] + " " + tmp[3];
    }
  }
};
</script>

<style scoped>

</style>
