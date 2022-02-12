<template>
  <div>
    <h1>New Arrivals</h1>
    <p>{{ message }}</p>
    <section class="bags_container">
      <article v-for="bag in bags" :key="bag[0]">
        <bag-card :bag="bag"></bag-card>
      </article>
    </section>
  </div>
</template>

<script>
import axios from "axios";
import BagCard from "./BagCard.vue";
export default {
  name: "bags-list",
  components: {
    BagCard,
  },
  data() {
    return {
      bags: [],
      message: "",
    };
  },
  created() {
    axios
      .request({
        url: `${process.env.VUE_APP_API_URL}/api/bags`,
        method: "GET",
      })
      .then((res) => {
        console.log(res);
        this.bags = res.data;
      })
      .catch((err) => {
        console.log(err);
        this.message = "Sorry, something went wrong!";
      });
  },
};
</script>

<style scoped>
.bags_container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
  gap: 30px;
  margin-top: 30px;
}
</style>
