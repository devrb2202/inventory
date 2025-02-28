<template>
    <div class="pa-4 text-center">
      <v-dialog v-model="dialog" max-width="600">
        <template v-slot:activator="{ props: activatorProps }">
          <v-btn
            class="text-caption font-weight-regular text-lg-overline"
            prepend-icon="mdi-plus"
            text="Add Category"
            variant="tonal"
            color="blue"
            v-bind="activatorProps"
          ></v-btn>
        </template>
  
        <v-card prepend-icon="mdi-account" title="Add User" style="overflow: initial; z-index: initial">
          <v-card-text>
            <v-row dense>
              <v-col cols="12" md="4" sm="6">
                <v-text-field label="First name*" required v-model="fname"></v-text-field>
              </v-col>
  
              <v-col cols="12" md="4" sm="6">
                <v-text-field label="Middle name" v-model="mname"></v-text-field>
              </v-col>
  
              <v-col cols="12" md="4" sm="6">
                <v-text-field label="Last name*" persistent-hint required v-model="lname"></v-text-field>
              </v-col>
  
              <v-col cols="12" md="4" sm="6">
                <v-text-field label="Email*" required v-model="email"></v-text-field>
              </v-col>
  
              <v-col cols="12" md="4" sm="6">
                <v-text-field label="Password*" type="password" required v-model="password"></v-text-field>
              </v-col>
            </v-row>
          </v-card-text>
          
          <v-divider></v-divider>
          <v-card-text v-if="errorMessage">
            Incomplete Form
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
  
            <v-btn text="Close" variant="plain" @click="dialog = false"></v-btn>
  
            <!-- Call the `submit` function when the "Add" button is clicked -->
            <v-btn color="primary" text="Add" variant="tonal" @click="submit"></v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>
  </template>

  <script setup>
  import { ref } from 'vue';
  
  import Swal from 'sweetalert2'

  const dialog = ref(false);
  const errorMessage = ref(false)
  // Local state for form inputs
  const fname = ref('');
  const mname = ref('');
  const lname = ref('');
  const email = ref('');
  const password = ref('');
  
  // Emit the new user data to the parent component
  const emit = defineEmits(['add-user']);
  
  const submit = () => {

    if(!fname.value || !mname.value || !lname.value || !email.value || !password.value){
        return errorMessage.value = true
    }
    
    const newUser = {
        firstname: fname.value,
        middlename: mname.value,
        lastname: lname.value,
        email: email.value,
        password: password.value,

    };

    Swal.fire({
        title: "Added Successfull!",
        icon: "success",
    });
  
    // Emit the new user data
    emit('add-user', newUser);
  
    // Reset the form fields
    fname.value = '';
    mname.value = '';
    lname.value = '';
    email.value = '';
    password.value = '';
    errorMessage.value = false
    // Close the dialog
    dialog.value = false;
  };

  watch([fname, lname, email, password], () => {
    errorMessage.value = false;
});


</script>






















<!-- <template>
    <div class="pa-4 text-center">
      <v-dialog
        v-model="dialog"
        max-width="600"
      >
        <template v-slot:activator="{ props: activatorProps }">
          <v-btn
            class="text-caption font-weight-regular text-lg-overline"
            prepend-icon="mdi-plus"
            text="Add Category"
            variant="tonal"
            color="blue"
            v-bind="activatorProps"
          ></v-btn>
        </template>
  
        <v-card
          prepend-icon="mdi-account"
          title="Add User"
        >
          <v-card-text>
            <v-row dense>
              <v-col
                cols="12"
                md="4"
                sm="6"
              >
                <v-text-field
                  label="First name*"
                  required
                  v-model="fname"
                ></v-text-field>
              </v-col>
  
              <v-col
                cols="12"
                md="4"
                sm="6"
              >
                <v-text-field
                  label="Middle name"
                  v-model="mname"
                ></v-text-field>
              </v-col>
  
              <v-col
                cols="12"
                md="4"
                sm="6"
              >
                <v-text-field
                  label="Last name*"
                  persistent-hint
                  required
                  v-model="lname"
                ></v-text-field>
              </v-col>
  
              <v-col
                cols="12"
                md="4"
                sm="6"
              >
                <v-text-field
                  label="Email*"
                  required
                  v-model="email"
                ></v-text-field>
              </v-col>
  
              <v-col
                cols="12"
                md="4"
                sm="6"
              >
                <v-text-field
                  label="Password*"
                  type="password"
                  required
                  v-model="password"
                ></v-text-field>
              </v-col>
  
            </v-row>
  
          </v-card-text>
  
          <v-divider></v-divider>
  
          <v-card-actions>
            <v-spacer></v-spacer>
  
            <v-btn
              text="Close"
              variant="plain"
              @click="dialog = false"
            ></v-btn>
  
            <v-btn
              color="primary"
              text="Add"
              variant="tonal"
              @click="submitted"
            ></v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>
  </template>
<script setup>

const dialog = ref(false)

const fname = defineModel('fname')
const mname = defineModel('mname')
const lname = defineModel('lname')
const email = defineModel('email')
const password = defineModel('password')
const submitted = defineModel('submitted')

defineProps({
    fname: String,
    mname: String,
    lname: String,
    email: String,
    password: String,
    submitted: String,
    
    
})


</script> -->