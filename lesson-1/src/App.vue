<template>
  <div class="app">
    <job-list :jobs="jobs"></job-list>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobList from "./components/JobList.vue";

// types
import Job from "./types/Job";

export default defineComponent({
  name: "App",
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>([
      { title: "Farmer", location: "Farm", salary: 30000, id: "1" },
      { title: "Doctor", location: "Hospital", salary: 60000, id: "2" },
    ]);
    return { jobs };
  },
  methods: {},
});
</script>
