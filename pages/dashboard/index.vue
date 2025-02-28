<template>
    <v-col cols="12">
        <v-row no-gutters>
            <v-col class="pa-2" v-for="(x, index) in cards" 
            :key="index" 
            :cols="cols[index].cols" 
            :sm="cols[index].sm"
            :md="cols[index].md"
            :lg="cols[index].lg"
            :xl="cols[index].xl"
            :xxl="cols[index].xxl"
            >
                <DashboardCard 
                :title="x.title"
                :count="x.count"
                :color="x.color"
                :icon="x.icon"
                :buttonTitle="x.buttonTitle"
                :actions="x.actions"
                />
            </v-col>     
           
            <v-col cols="12">
                <DashboardDataTable />
            </v-col>
             
        </v-row>
    </v-col>
      
</template>

<script setup>

const cols = ref([
    {cols: '12', sm: '6', md: '4', lg: '3', xl: '2', xxl: '2'},
    {cols: '12', sm: '6', md: '4', lg: '3', xl: '2', xxl: '2'},
    {cols: '12', sm: '6', md: '4', lg: '3', xl: '2', xxl: '2'},
    {cols: '12', sm: '6', md: '4', lg: '3', xl: '2', xxl: '2'},
    {cols: '12', sm: '6', md: '4', lg: '3', xl: '2', xxl: '2'},
    {cols: '12', sm: '6', md: '4', lg: '3', xl: '2', xxl: '2'},
    {cols: '12', sm: '6', md: '4', lg: '3', xl: '2', xxl: '2'},
  
])

const cards = ref([
    {title: 'System Users',count: '2', icon: 'mdi-incognito', color: 'green-darken-4', buttonTitle: 'more info', actions: user},
    {title: 'Category',count: '125', icon: 'mdi-sort', color: 'red', buttonTitle: 'more info', actions: category},
    {title: 'Products',count: '67', icon: 'mdi-bank', color: 'blue', buttonTitle: 'more info', actions: products},
    {title: 'Customers',count: '8', icon: 'mdi-account-group', color: 'blue-grey-darken-4', buttonTitle: 'more info', actions: out},
    {title: 'Supplier',count: '192', icon: 'mdi-poll', color: 'brown-darken-4', buttonTitle: 'more info', actions: out},
    {title: 'Total Purchase',count: '192', icon: 'mdi-cart', color: 'green-darken-3', buttonTitle: 'more info', actions: out},
    {title: 'Outgoing',count: '192', icon: 'mdi-airplane-clock', color: 'grey', buttonTitle: 'more info', actions: out},
])

function user(){
    alert('System Users')
}
function category(){
    alert('System Category')
}
function products(){
    alert('System Products')
}
function out(){
    alert('System Outgoing')
}

definePageMeta({
    layout: 'main'
})

</script>