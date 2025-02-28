<template>
    <v-card
      class="mx-auto pa-2"
      variant="text"
    >
      <v-list class="text-caption text-lg-overline">
        <v-list-subheader>REPORTS</v-list-subheader>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :value="item"
          :to="item.to"
          color="blue"
        >
          <template v-slot:prepend>
            <v-icon :icon="item.icon"></v-icon>
          </template>
          <v-list-item-title 
          v-text="item.text" 
          class="text-caption text-lg-overline"
          >
          </v-list-item-title>
        </v-list-item>
      </v-list>
    </v-card>
  </template>
<script setup>

const items = ref([
        { text: 'Information', icon: 'mdi-information-outline', to: '/' },
        { text: 'Dashboard', icon: 'mdi-view-dashboard', to: '/dashboard' },
        { text: 'Category', icon: 'mdi-receipt-text-outline', to: '/category' },
        { text: 'Products', icon: 'mdi-blur-linear', to: '/products'},
])
    
</script>
