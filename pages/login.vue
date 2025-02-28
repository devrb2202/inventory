<template>
    <AccountForm 
    title="Welcome Back!"
    buttonTitle="login"
    :isSubmit="fired"
    :inputs="userLogin"
    >
        <template v-slot:extra>
            <nuxt-link to="/register">Register Account</nuxt-link>
        </template>
    </AccountForm>
</template>

<script setup>

const username = ref('')
const password = ref('')

const userLogin = ref([
    {label: 'Username', placeholder: 'Enter your username', icon: 'mdi-account', model: username , type: 'text'},
    {label: 'Password', placeholder: 'Enter your password', icon: 'mdi-lock', model: password , type: 'password'}
])

function fired() {
    alert('Function fIred')
    console.log('Function FIred')
}


</script>