<template>
  <v-app>
    <v-navigation-drawer
      v-if="user != null"
      v-model="drawerShown"
      temporary app>

      <v-list-item>
        <v-list-item-content>
          <v-icon size="100">mdi-login</v-icon>
          <v-list-item-title class="text-center">
            Login to view your jobs
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>
      <v-list
        dense
        nav>
        <router-link v-for="item in routes"
                     :to="item.route"
                     @click="drawerShown = false"
                     style="text-decoration: none; color: inherit;"
                     :key="item.name">
          <v-list-item link>
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>
                {{ item.name }}
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-divider/>
        </router-link>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <v-app-bar-nav-icon v-if="user != null"
                          @click="drawerShown = !drawerShown"/>
      <v-toolbar-title>
        Reminder App
      </v-toolbar-title>


      <v-spacer></v-spacer>
      <v-dialog
        v-model="dialog"
        width="500"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="white "
            outlined
            v-bind="attrs"
            v-on="on"
          >
            <span class="mr-2">
              Get Started
            </span>
            <v-icon>mdi-login</v-icon>
          </v-btn>
        </template>

        <v-card>
          <v-card-title class="text-h5 lighten-2">
            Get started
          </v-card-title>

          <v-tabs
            center-active
            v-model="tab"
          >
            <v-tab
              key="login"
            >
              LOGIN
            </v-tab>
            <v-tab
            key="register">
              REGISTER
            </v-tab>
          </v-tabs>

          <v-tabs-items v-model="tab">
            <v-tab-item
            key="login">
              <v-card
                class="pa-5"
              >
              <v-form
                  ref="form"
                  v-model="valid"
                  lazy-validation
                >
                  <v-text-field
                    v-model="username"
                    label="Username"
                    required
                  ></v-text-field>

                  <v-text-field
                    v-model="password"
                    label="Password"
                    required
                    type="password"
                  ></v-text-field>

                  <v-btn
                    color="primary"
                    class="mr-4 text-right"
                  >
                    Submit
                  </v-btn>
              </v-form>
              </v-card>
            </v-tab-item>

              <v-tab-item
                key="register">
                <v-card
                  class="pa-5"
                >
                  <v-form
                    ref="form"
                    v-model="valid"
                    lazy-validation
                  >
                    <v-text-field
                      v-model="username"
                      label="Username"
                      required
                    ></v-text-field>
                    <v-text-field
                      v-model="email"
                      label="Email"
                      required
                    ></v-text-field>
                    <v-text-field
                      v-model="password"
                      label="Password"
                      required
                      type="password"
                    ></v-text-field>

                    <v-btn
                      color="primary"
                      class="mr-4 text-right"
                    >
                      Submit
                    </v-btn>
                  </v-form>
                </v-card>
            </v-tab-item>
          </v-tabs-items>
        </v-card>
      </v-dialog>
    </v-app-bar>

    <v-content class="px-15">
      <router-view/>
    </v-content>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "App",
  components: {},
  data: () => ({
    drawerShown: false,
    user: {
      name: "YourName",
    },
    tab: null,
      items: [
        "web", "shopping", "videos", "images", "news",
      ],
      text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
  }),
  computed: {
    routes(): Array<{
      name: string;
      route: string;
      icon: string;
    }> {
      // Add routes here to correspond to router.ts
      return [
        {
          name: "About",
          route: "/",
          icon: "mdi-file-table-box",
        },
        {
          name: "Jobs",
          route: "/jobs",
          icon: "mdi-email",
        },
      ];
    },
  }
});
</script>
