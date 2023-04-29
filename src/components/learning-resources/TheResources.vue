<template>
    <base-card>
    <base-button @click="setselectedTab('stored-resources')">Stored Resources</base-button>
    <base-button @click="setselectedTab('add-resource')">Add Resource</base-button>
    </base-card>
    <component :is="selectedTab"></component>

</template>

<script>
import storedResources from './StoredResources.vue';
import AddResource from './AddResource.vue';
export default {
    components:{
        storedResources,
        AddResource
    },
    data() {
        return{
            selectedTab: 'stored-resources'
        };    
    },
    methods:{
        setselectedTab(tab){
            this.selectedTab = tab;
        }
    }
}
</script>