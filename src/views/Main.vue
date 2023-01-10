<template>
  <v-container fluid style="width: 60%">
      <h1 class="pa-10 text-center font-weight-light"
          style="font-size: 3rem"
      >
        Welcome to ReminderApp
      </h1>

      <h4 class="text-center font-weight-medium"
          style="font-size: 1.5rem"
      >
        A tool to set flexible long term, recurring reminders sent straight to your inbox.
      </h4>

      <v-row
        justify="center"
        class="mt-5 "

      >
        <v-col
          cols="4"
        >
          <v-card >
            <v-card-title>
              Reliable
            </v-card-title>
            <v-card-text>
              Don't want to miss the next lunar eclipse? ReminderApp can be used to send reminders months in advance. Set up a mailing list to notify your friends too!
            </v-card-text>
          </v-card>
        </v-col>

        <v-col
          cols="4"
        >
          <v-card >
            <v-card-title class="darken-5 ">
              Flexible
            </v-card-title>
            <v-card-text>
              Timing and scheduling of reminders can be configured with cronjob syntax or through a friendly GUI.
            </v-card-text>
            <v-card-text>

            </v-card-text>
          </v-card>
        </v-col>


        <v-col
          cols="4"
        >
          <v-card >
            <v-card-title class="darken-5 ">
              Expressive
            </v-card-title>
            <v-card-text>
              Style your emails with HTML to give it an extra flair.
            </v-card-text>
            <v-card-text>

            </v-card-text>
          </v-card>
        </v-col>
      </v-row>

    <v-card
      class="mt-15 pa-5"
    >
      <v-card-title>
        Got queries? ​
        <b> Contact Us!</b>
      </v-card-title>
                  <v-form
                    ref="form"
                    v-model="valid"
                    lazy-validation
                  >

                    <v-row>
                      <v-col cols="6">
                    <v-text-field
                      v-model="Name"
                      label="Username"
                      required
                    ></v-text-field>
                      </v-col>
                      <v-col cols="6">
                    <v-text-field
                      v-model="email"
                      label="Email"
                      required
                    ></v-text-field>
                      </v-col>
                    </v-row>
                    <v-textarea
                      v-model="query"
                      label="Write a short description of your query"
                      required
                    ></v-textarea>

                    <v-btn
                      color="primary"
                      class="mr-4 text-right"
                    >
                      Submit
                    </v-btn>
                  </v-form>

    </v-card>

  </v-container>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Main",
  data: function () {
    return {
      name: "",
      mainOut: ""
    };
  },
});
</script>
