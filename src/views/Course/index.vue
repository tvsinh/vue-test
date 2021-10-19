<template>
  <div class="course mt-5">
    <b-container>
      <div class="row">
        <Left class="col-lg-3" />
        <Right class="col-lg-9" />
      </div>
    </b-container>
  </div>
</template>

<script>
import Left from "./Left";
import Right from "./Right";
export default {
  name: "Course",
  data: function () {
    return {
      categories: 0,
    };
  },
  components: {
    Left,
    Right,
  },
};
</script>

<style lang="scss" scoped></style>
