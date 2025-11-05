<template>
    <div>
        <v-app>

             <v-navigation-drawer
        expand-on-hover
        permanent
        rail
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
          <v-list-item prepend-icon="mdi-folder" title="My Files" value="myfiles"></v-list-item>
          <v-list-item prepend-icon="mdi-account-multiple" title="Shared with me" value="shared"></v-list-item>
          <v-list-item prepend-icon="mdi-star" title="Starred" value="starred"></v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-app-bar :elevation="2">
  <template v-slot:prepend>
    <v-app-bar-nav-icon></v-app-bar-nav-icon>
  </template>

  <v-app-bar-title>Application Bar</v-app-bar-title>
</v-app-bar>



        </v-app>
    </div>
</template>