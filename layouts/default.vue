<template>
    <v-app>
        <v-app-bar class="bg-teal-darken-4">
            <v-row class="justify-center" no-gutters>
                <v-col cols="12" sm="6" class="d-flex justify-space-between pa-4">
                    <v-btn class="bg-teal-darken-4 text-caption text-sm-caption text-lg-overline" to="/" prepend-icon="mdi-home">Home
                    </v-btn>
                    <v-btn class="bg-teal-darken-4 text-caption text-sm-caption text-lg-overline " to="/login" prepend-icon="mdi-account">Login
                    </v-btn>
                </v-col>
            </v-row>
        </v-app-bar>
        <v-main>
            <v-container class="d-flex h-100 align-center justify-center">
                <slot />
            </v-container>
        </v-main>
    </v-app>
   
</template>


<script>



</script>


<style scoped>

.text-color {
    color: 'white'
}


</style>