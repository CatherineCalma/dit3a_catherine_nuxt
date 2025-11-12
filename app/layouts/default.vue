<template>
    <div>
        <v-app>

             <v-navigation-drawer
             v-model="drawer"
        
      >
        <v-list>
          <v-list-item
            prepend-avatar="https://i.pinimg.com/736x/ee/74/0e/ee740ec12223ab4e011d4454c8ca7523.jpg"
            subtitle="DIT-3A"
            title="Catherine Joy P. Calma"
          ></v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item to="/" prepend-icon="mdi-view-dashboard" title="Dashboard" value="dashboard"></v-list-item>
          <v-list-item to="inventory" prepend-icon="mdi-account-multiple" title="Inventory" value="inventory"></v-list-item>
          <v-list-item to="category"prepend-icon="mdi-shape" title="Category" value="category"></v-list-item>
          <v-list-item to="files" prepend-icon="mdi-file-multiple" title="Files" value="files"></v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-app-bar :elevation="2">
  <template v-slot:prepend>
    <v-app-bar-nav-icon @click.stop="drawer =! drawer"></v-app-bar-nav-icon>
  </template>

  <v-app-bar-title>Application Bar</v-app-bar-title>
</v-app-bar>

<v-main>
  <v-container fluid>
    <slot/>
  </v-container>
</v-main>

        </v-app>

    </div>
</template>

<script setup>
const drawer =ref(true)
</script>