<template>
   <v-col cols="12" sm="4">
    <v-form @prevent.submit="isSubmit">
        <v-card >
            <v-card-text class="text-h2 text-center text-h4 text-sm-h4 text-lg-h2">{{ title }}</v-card-text>
                <v-card-text>
                    <v-text-field v-for="(input, index) in inputs" :key="index"
                    :label="input.label"
                    :placeholder="input.placeholder"
                    :prepend-inner-icon="input.icon"
                    :type="input.type"
                    density="compact"
                    variant="outlined"
                    color="teal-darken-4"
                    v-model="input.model"
                    class="text-caption text-lg-overline"
                    >
                    </v-text-field>
                    <v-btn 
                    block 
                    color="teal-darken-4"
                    type="submit"
                    prepend-icon="mdi-login"
                    class="text-caption text-lg-overline"
                    >
                      {{ buttonTitle }}
                    </v-btn>
                </v-card-text>
            <v-card-text class="text-right">
                <slot name="extra"></slot>
            </v-card-text>
        </v-card>
    </v-form>
   </v-col>
</template>


<script setup>

defineProps({
    title: String,
    label: String,
    color: String,
    placeholder: String,
    icon: String,
    type: String,
    inputs: {
        type: Array,
        required: true
    },
    // Button Props
    isSubmit: String,
    buttonTitle: String

})

</script>