<template>
    <v-card max-width="450" class="pa-3" :color="color">
        <v-card-text class="text-caption text-lg-overline">
            <v-row class="justify-space-between">
                <div>
                    <h1>{{ count }}</h1>
                    <p>{{ title }}</p>
                </div>
                <div>
                    <v-icon size="60" :icon="icon" color="grey-lighten-2"></v-icon>
                </div>
            </v-row>
        </v-card-text>
        <template v-slot:actions>
            <v-btn @click="actions" class="text-caption text-lg-overline" block>{{ buttonTitle }}</v-btn>
        </template>
    </v-card>
</template>

<script setup>

defineProps({
    count: String,
    title: String,
    icon: String,
    actions: String,
    buttonTitle: String,
    color: String,
   
})

</script>













<!-- 



<template>
    <v-card max-width="450" class="pa-3" v-for="(loops, index) in loop" :key="index" :color="loops.color">
        <v-card-text class="text-overline">
            <v-row class="justify-space-between">
                <div>
                    <h1>{{ loops.count }}</h1>
                    <p>{{ loops.title }}</p>
                </div>
                <div>
                    <v-icon size="60" :icon="loops.icon" color="grey-lighten-2"></v-icon>
                </div>
            </v-row>
        </v-card-text>
        <template v-slot:actions>
            <v-btn @click="loops.actions">{{ loops.buttonTitle }}</v-btn>
        </template>
    </v-card>
</template>

<script setup>

defineProps({
    count: String,
    title: String,
    icon: String,
    actions: String,
    buttonTitle: String,
    color: String,
    loop : {
        type: Array,

    }
})

</script> -->









