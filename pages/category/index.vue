<template>
    <v-col cols="12">
        <v-row class="justify-end">
            <CategoryDialog 
            @add-user="addUser" 
            />
          
        </v-row>
        {{ names }}
        <CategoryDataTable 
        :head="headers"
        :name="names"
        v-model:search="search"
        />
    </v-col>

</template>


<script setup>

import Swal from 'sweetalert2'

const names = ref([])

const search = ref('')

const headers = ref([
    { align: 'start', key: 'firstname', sortable: false, title: 'First Name'},
    { key: 'middlename', title: 'Middle Name' },
    { key: 'lastname', title: 'Last Name' },
    { key: 'email', title: 'Email' },
    { key: 'password', title: 'Password' },
])

// Function to add a new user to the `names` array
const addUser = (newUser) => {
 
  names.value.push(newUser);
};


definePageMeta({
    layout: 'main'
}) 

</script>
