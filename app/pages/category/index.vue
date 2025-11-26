<template>
  <v-card
    title="Category"
    flat
  >
    <template v-slot:text>
      <v-text-field
        v-model="search"
        label="Search"
        prepend-inner-icon="mdi-magnify"
        variant="outlined"
        hide-details
        single-line
      ></v-text-field>
    </template>

    <v-data-table
      :headers="headers"
      :items="category.data"
      :search="search"
    ></v-data-table>
  </v-card>
</template>

<script setup>
   
  const { data: category } = await useFetch('http://localhost:1337/api/categories');

  const search = ref('')
  const headers = [
    
    { key: 'category_name', title: 'Category' },
    { key: 'description', title: 'Description' },
    { key: 'createdAt', title: 'Date Created' },


  ]
  const desserts = [
    
  ]
</script>