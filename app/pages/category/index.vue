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
    {
      align: 'start',
      key: 'name',
      sortable: false,
    
    },
    { key: 'category_name', title: 'Category Name' },
    { key: 'description', title: 'Description' },
    { key: 'category_id', title: 'Category ID' },
    { key: 'date_created', title: 'Date Created' },
  ]
  
</script>