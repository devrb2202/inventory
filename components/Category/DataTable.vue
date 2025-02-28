<template>
    <v-card
      class="text-overline"
      flat
    >
      <template v-slot:text>
        <v-text-field
          class="text-caption text-lg-overline"
          label="Search"
          prepend-inner-icon="mdi-magnify"
          variant="outlined"
          hide-details
          single-line
          density="compact"
          v-model="search"
        ></v-text-field>
      </template>
  
      <v-data-table 
        class="text-caption text-lg-overline"
        :headers="head"
        :items="name"
        :search="search"
      ></v-data-table>
    </v-card>
  </template>
<script setup>



// const search = ref('')

// const names = ref([])
// const headers = ref([
//         { align: 'start', key: 'firstname', sortable: false, title: 'First Name'},
//         { key: 'middlename', title: 'Middle Name' },
//         { key: 'lastname', title: 'Last Name' },
//         { key: 'email', title: 'Email' },
//         { key: 'password', title: 'Password' },

// ])

const search = defineModel('search');

defineProps({
  
    name: {
        type: Array
    },
    head: {
        type: Array
    }
})




// const names = ref([
//         { firstname: 'Frozen Yogurt', middlename: 'Dela Cruz', lastname: 'Doe', email: 'gdsadg@gmail.com', password: 'dsadasd'},
//         { firstname: 'dsadasdas', middlename: 'Dela Cruz', lastname: 'Doe23', email: 'g2232dsadg@gmail.com', password: 'dsadasd'},
//         { firstname: 'Frozen Yo3213gurt', middlename: 'Dela 45435Cruz', lastname: 'Doe', email: 'gds15551adg@gmail.com', password: 'dsadasd'},
//         { firstname: 'A', middlename: 'Dz', lastname: 'B', email: 'gds15551adg@gmail.com', password: 'dsadasd'},
// ])

        
       
    
</script>