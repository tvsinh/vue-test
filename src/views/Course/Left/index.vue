<template>
  <div class="">
    <span>Bộ lọc</span>
    <div>
      <p>Thông tin khóa học</p>
      <p>Khoá học</p>
      <p>Giảng viên</p>
      <div>
        <p>Từ ngày</p>
        <p>Đến ngày</p>
      </div>
      <p>Chủ đề</p>
      <CategoryFilter />
    </div>
  </div>
</template>

<script>
import CategoryFilter from "./CategoryFilter";
import { categories } from "../Data";
export default {
  name: "Left",
  data: function () {
    return {
      categories: categories,
    };
  },
  components: {
    CategoryFilter,
  },
};
</script>

<style scoped></style>
