<template>
  <div>
    <article class="bag_card">
      <img :src="bag[3]" :alt="bag[1]" />
      <h3>{{ bag[1] }}</h3>
      <p>{{ bag[2] }}</p>
      <div class="buttons">
        <button class="button">Add Item</button>
        <button class="button">Remove Item</button>
      </div>
    </article>
  </div>
</template>

<script>
export default {
  name: "bag-card",
  props: {
    bag: Array,
  },
};
</script>

<style scoped>
.buttons {
  display: flex;
  justify-content: center;
  margin: 10px;
}
.button {
  width: 100px;
  height: inherit;
}
</style>
