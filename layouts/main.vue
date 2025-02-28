<template>
    <v-app id="inspire">
        <v-navigation-drawer v-model="drawer" class="bg-grey-darken-4">
        <!--  -->
            <div class="d-flex justify-center bg-teal-darken-4">
                <v-card height="63" class="d-flex align-center" variant="text">
                    <v-card-text class="text-caption text-lg-overline">
                        Inventory System
                    </v-card-text>
                </v-card>  
            </div>
            <div>
                <NavigationLeft />
            </div>
            
        </v-navigation-drawer>

        <v-app-bar class="bg-teal-darken-3">
            <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

            <!-- <v-app-bar-title class="text-caption text-lg-overline">Application</v-app-bar-title> -->
        </v-app-bar>

        <v-main>
            <v-container>
                <slot></slot>
            </v-container>
        </v-main>
    </v-app>
</template>

<script setup>
import { ref } from 'vue'

const drawer = ref(null)
</script>
