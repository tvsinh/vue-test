<template>
  <div>
    <div>
      <input
        type="checkbox"
        :id="category.id"
        :value="category.categoryName"
        v-model="checkedName"
        @click="setActive(active)"
      />
      <label :for="category.id" class="ml-2">{{ category.categoryName }}</label>
    </div>
    <div
      v-show="active"
      v-for="subCategory in category.subCategory"
      :key="subCategory"
      class="ml-3"
    >
      <SubCategory :subCategory="subCategory" />
    </div>
  </div>
</template>

<script>
import SubCategory from "./SubCategory.vue";

export default {
  name: "Category",
  props: {
    category: Object,
  },
  data: function () {
    return {
      active: false,
      checkedName: [],
    };
  },
  components: {
    SubCategory,
  },
  methods: {
    setActive(active) {
      this.active = !active;
    },
  },
};
</script>

<style>
input[type="checkbox"] {
  cursor: pointer;
  width: 18px;
  height: 18px;
  border: 1.5px solid #a6a8b0;
  border-radius: 3px;
  vertical-align: baseline;
}
</style>
