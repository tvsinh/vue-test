<template>
  <div class="course">
    <div class="course_shadow">
      <div class="course_box_image">
        <!-- <img :src="course.imageUrl" alt="Course Image" /> -->
        <img
          src="../../Img/learner-student-at-home-work-study-feat 2.png"
          alt="Course Image"
          width="100%"
          class="course_image"
        />
        <p class="course_title">{{ course.title }}</p>
      </div>
      <div class="content">
        <div class="d-flex content_item">
          <div class="icon mr-2">
            <b-icon icon="calendar2"></b-icon>
          </div>
          <p class="mr-2" style="color: #227ff4">
            {{ course.startTime | formatTime }}
          </p>
          <p>{{ course.endTime | formatDate }}</p>
        </div>
        <div class="d-flex content_item">
          <div class="icon mr-2">
            <b-icon icon="calendar2"></b-icon>
          </div>
          <p class="mr-2" style="color: #ea5455">
            {{ course.startTime | formatTime }}
          </p>
          <p class="">{{ course.endTime | formatDate }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import moment from "moment";
export default {
  name: "CourseItem",
  props: {
    course: Object,
  },
  filters: {
    formatTime: function (value) {
      if (value) {
        return moment(String(value)).format("HH:mm");
      }
    },
    formatDate: function (value) {
      if (value) {
        return moment(String(value)).format("DD/MM/YYYY");
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.course {
  padding-left: 15px;
  padding-right: 15px;
  margin-bottom: 30px;
}
.course_shadow {
  border-radius: 6px;
  box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
}
.course_box_image {
  position: relative;
  color: white;
}
.course_box_image::before {
  position: absolute;
  content: "";
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.15);
}
.course_title {
  padding: 0 10px;
  position: absolute;
  bottom: 0;
  font-weight: 500;
  font-size: 24px;
  line-height: 29px;
}
.content {
  padding: 10px;
}

.icon {
  transform: translateY(-1px);
}
</style>
