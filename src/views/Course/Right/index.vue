<template>
  <div>
    <div>
      <p>Danh sách khóa học</p>
      <div>
        <b-input-group-append class="box_search">
          <b-form-input
            type="text"
            placeholder="Tìm kiếm..."
            class="input"
          ></b-form-input>
          <div class="icon_search">
            <b-icon icon="search" />
          </div>
        </b-input-group-append>
      </div>
      <div class="d-flex flex-wrap mt-4 courses">
        <CourseItem
          v-for="(course, index) in courses"
          :key="index"
          :course="course"
          class="col-lg-4"
        />
      </div>
    </div>
  </div>
</template>

<script>
import CourseItem from "./CourseItem";
import { courses } from "../Data";
export default {
  name: "Right",
  data() {
    return {
      courses: courses,
    };
  },
  components: {
    CourseItem,
  },
};
</script>

<style scoped>
.box_search {
  position: relative;
  box-shadow: rgba(0, 0, 0, 0.1) 0px 0px 10px;
  border-radius: 6px;
  height: 58px;
}
.input {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  padding-left: 20px;
  outline: none;
  border: none;
  width: 94%;
}
input:focus {
  box-shadow: none;
  outline: 0;
  border: 0;
}
.icon_search {
  position: absolute;
  right: 20px;
  top: 50%;
  transform: translateY(-50%);
}
.courses {
  margin-left: -15px;
  margin-right: -15px;
}
</style>
