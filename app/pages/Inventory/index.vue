<template>
  <v-card
    title="Invetory"
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
      :items="inventory.data"
      :search="search"
    ></v-data-table>
  </v-card>
</template>
<script setup>

  const search = ref('')
  const { data: inventory } = await useFetch('http://localhost:1337/api/inventories');
  const headers = [
    { key: 'product_name', title: 'Product' },
    { key: 'prouct_description', title: 'Description' },
    { key: 'quantity', title: 'Quantity' },
    { key: 'unit', title: 'Unit' },
    { key: 'condition', title: 'Conditon' },
    { key: 'location', title: 'Quantity' },
    { key: 'acquisition_date', title: 'Acquisition Date' },
    { key: 'acquisition_cost', title: 'Acquisition Cost' },
    { key: 'total_cost', title: 'Total cost' },
    { key: 'remarks', title: 'Remarks' },
    { key: 'category', title: 'Category' },
  ];
</script>