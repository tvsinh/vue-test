<template>
  <div>
    <div>
      <input
        type="checkbox"
        :id="subCategory.name"
        :value="subCategory.name"
        v-model="checkedSub"
        @click="setActive(activeSub)"
      />
      <label :for="subCategory.name" class="ml-2">{{ subCategory.name }}</label>
    </div>
    <div
      v-show="activeSub"
      v-for="subItem in subCategory.subItem"
      :key="subItem"
      class="ml-3"
    >
      <input
        type="checkbox"
        :id="subItem.item"
        :value="subItem.item"
        v-model="checkedItems"
      />
      <label :for="subItem.item" class="ml-2">{{ subItem.item }}</label>
    </div>
  </div>
</template>

<script>
export default {
  name: "SubCategory",
  props: {
    subCategory: Object,
  },
  data: function () {
    return {
      activeSub: false,
      checkedSub: [],
      checkedItems: [],
    };
  },

  methods: {
    setActive(activeSub) {
      this.activeSub = !activeSub;
    },
  },
};
</script>

<style scoped>
.title {
  display: block;
}
.subTitle {
  display: block;
}
</style>
