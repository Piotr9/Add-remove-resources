<template>
  <div>
    <base-card>
      <base-button @click="setSelectedTab('stored-resources')" :mode="selectedTab === 'stored-resources' ? null : 'flat'"
        >Stored Resources</base-button
      >
      <base-button @click="setSelectedTab('add-resource')" :mode="selectedTab === 'add-resource' ? null : 'flat'"
        >Add Resources</base-button
      >
    </base-card>
    <keep-alive>
        <component :is="selectedTab"></component>
    </keep-alive>
  </div>
</template>

<script>
import StoredResources from "./StoredResources.vue";
import AddResource from "./AddResource.vue";

export default {
  components: {
    StoredResources,
    AddResource,
  },
  data() {
    return {
      selectedTab: "stored-resources",
      storedResources: [
        {
          id: "official-guide",
          title: "Official Guide",
          description: "The Official Vue.js documentation.",
          link: "https://vuejs.org",
        },
        {
          id: "google",
          title: "Google",
          description: "Learn to Google...",
          link: "https://google.com",
        },
      ],
    };
  },
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource
    };
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },
    addResource(title, description, link) {
        const newResource = {
            id: new Date().toISOString(),
            title: title,
            description: description,
            link: link
        };
        this.storedResources.unshift(newResource);     //unshift() = push() on the begining
        this.selectedTab = 'stored-resources';
    }
  },
};
</script>
