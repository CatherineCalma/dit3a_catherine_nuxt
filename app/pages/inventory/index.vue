<template>
  <v-card
    title="Inventory"
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

    <!-- Selectable Category-->
     <v-select
     v-model="selectedCategory"
        clearable
        label="Select"
       :items="category.data"
       variant="outlined"
       item-title="category_name"
       item-value="id"
       class="mx-4"
    ></v-select>

    <v-data-table
      :headers="headers"
      :items="filteredCategory"
      :search="search"
    ></v-data-table>
  </v-card>
</template>


<script setup>
   const { data: inventory } = await useFetch('http://localhost:1337/api/inventories?populate=category');

   const { data: category } = await useFetch('http://localhost:1337/api/categories');

   const selectedCategory = ref(null);

  const search = ref('')
  const headers = [
    {
      align: 'start',
      key: 'name',
      sortable: false,
    
    },
    { key: 'product_name', title: 'Product Name' },
    { key: 'product_description', title: 'Product Description' },
    { key: 'quantity', title: 'Quantity' },
    { key: 'unit', title: 'Unit' },
    { key: 'condition', title: 'Condition' },
    { key: 'Location', title: 'Location' },
    { key: 'acquisition_date', title: 'Acquisition Date' },

  ]

  const filteredCategory = computed(() =>{
    // Show all inventory products if not selected category 

    if(!selectedCategory.value){
      return inventory.value.data;
    }else{
      return inventory.value.data.filter(item =>
        items.category.id == selectedCategory.value
      )
    }

  })
</script>