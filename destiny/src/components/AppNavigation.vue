<template>
  <span>
    <v-navigation-drawer
      app
      v-model="drawer"
      class="indigo"
      dark
      disable-resize-watcher
    >
      <v-list>
        <template v-for="(item, index) in items">
          <v-list-tile :key="index">
            <v-list-tile-content>
              {{ item.title }}
            </v-list-tile-content>
          </v-list-tile>
          <v-divider :key="`divider-${index}`"></v-divider>
        </template>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app color="indigo darken-4" dark>
      <v-app-bar-nav-icon
        class="hidden-md-and-up"
        @click="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <v-spacer class="hidden-md-and-up"></v-spacer>
      <v-toolbar-title>{{ appTitle }}</v-toolbar-title>
      <v-btn text class="hidden-sm-and-down">Overview</v-btn>
      <v-btn text class="hidden-sm-and-down">Orders</v-btn>
      <v-btn text class="hidden-sm-and-down">Batches</v-btn>
    </v-app-bar>
  </span>
</template>

<script>
export default {
  name: 'AppNavigation',
  data() {
    return {
      appTitle: 'Redania',
      drawer: false,
      items: [{ title: 'Overview' }, { title: 'Orders' }, { title: 'Batches' }],
    };
  },
};
</script>

<style scoped></style>
