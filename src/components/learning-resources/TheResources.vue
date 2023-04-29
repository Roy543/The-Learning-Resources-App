<template>
  <base-card>
    <base-button
      @click="setselectedTab('stored-resources')"
      :mode="storedResButtonMode"
      >Stored Resources</base-button
    >
    <base-button @click="setselectedTab('add-resource')" :mode="addResButtonMode"
      >Add Resource</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import storedResources from './StoredResources.vue';
import AddResource from './AddResource.vue';
export default {
  components: {
    storedResources,
    AddResource,
  },
  computed:{
    storedResButtonMode(){
        return this.selectedTab === 'stored-resources' ? null : 'flat';
    },
    addResButtonMode(){
        return this.selectedTab === 'add-resource' ? null : 'flat';
    }
  },
  data() {
    return {
      selectedTab: 'stored-resources',
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'Official VueJS Documentation.',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to Google.',
          link: 'https://google.org',
        },
      ],
    };
  },
  provide() {
    return {
      resources: this.storedResources,
    };
  },
  methods: {
    setselectedTab(tab) {
      this.selectedTab = tab;
    },
  },
};
</script>