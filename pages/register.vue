<template>
    <AccountForm 
    title="Welcome to Our App"
    buttonTitle="Register"
    :isSubmit="fired"
    :inputs="userRegister"
    />
</template>


<script setup>

const email = ref('')
const username = ref('')
const password = ref('')

const userRegister = ref([
    {label: 'Email', placeholder: 'Enter your email', icon: 'mdi-at', model: email , type: 'email'},
    {label: 'Username', placeholder: 'Enter your username', icon: 'mdi-account', model: username , type: 'text'},
    {label: 'Password', placeholder: 'Enter your password', icon: 'mdi-lock', model: password , type: 'password'}
])

function fired() {
    alert('Function FIred')
    console.log('Function FIred')
}

</script>