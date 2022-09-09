<template>
  <div class="app">
    <header>
      <div class="order">
        <button v-on:click="handeClick('title')">Order by title</button>
        <button v-on:click="handeClick('salary')">Order by salary</button>
        <button v-on:click="handeClick('location')">Order by location</button>
      </div>
    </header>
    <job-list :jobs="jobs" :order="order"></job-list>
  </div>
</template> 

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobList from "./components/JobList.vue";

// types
import Job from "./types/Job";
import OrderTerm from "./types/OrderTerm";

export default defineComponent({
  name: "App",
  components: { JobList },

  setup() {
    const jobs = ref<Job[]>([
      { title: "Farmer", location: "Farm", salary: 30000, id: "1" },
      { title: "Doctor", location: "Hospital", salary: 60000, id: "2" },
    ]);

    const order = ref<OrderTerm>("title");

    const handeClick = (term: OrderTerm) => {
      order.value = term;
      console.log(order.value);
    };

    return { jobs, handeClick, order };
  },
  methods: {},
});
</script>

<style>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
</style>
