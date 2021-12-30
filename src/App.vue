<template>
  <v-app>
    <v-main>
      <Home />
    </v-main>
    <v-bottom-navigation :value="value" color="pink" grow fixed>
      <v-btn class="pa-7" text>
        <span>Home</span>
        <v-icon>mdi-home-outline</v-icon>
      </v-btn>
      <v-btn class="pa-7" text>
        <span>Chat</span>
        <v-icon>mdi-chat-processing-outline </v-icon>
      </v-btn>
      <v-btn class="pa-7" text>
        <span>Favorites</span>
        <v-icon>mdi-heart-outline</v-icon>
      </v-btn>
      <v-btn class="pa-7" text>
        <span>Account</span>
        <v-icon>mdi-account-outline</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </v-app>
</template>

<script>
import Home from "./components/Home";

export default {
  name: "App",
  components: {
    Home,
  },
  data: () => ({ value: 0 }),
};
</script>

<style>
::-webkit-scrollbar {
  display: none;
}
</style>
