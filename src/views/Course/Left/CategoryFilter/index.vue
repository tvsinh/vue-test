<template>
  <div class="">
    <div v-for="category in categories" :key="category">
      <Category :category="category" />
    </div>
  </div>
</template>

<script>
import Category from "./Category.vue";
import { categories } from "../../Data";
export default {
  name: "CategoryFilter",
  data() {
    return {
      categories: categories,
    };
  },
  components: {
    Category,
  },
};
</script>

<style></style>
