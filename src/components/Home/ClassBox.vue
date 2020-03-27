<template>
  <div class="box box-sm">
    <div class="header">
      <box-icon name="school" type="solid" color="#330066" size="lg"></box-icon>
      <div>
        <button class="button-primary shrink">View Schedule</button>
        <button class="button-primary shrink">Register</button>
      </div>
    </div>
    <div class="align bold">
      <p>Course</p>
      <p>Credits</p>
      <p>Grade</p>
    </div>
    <div v-for="course in courses" :key="course.id">
      <div class="spacer"></div>
      <div class="align">
        <p>{{course.pantone_value}}</p>
        <p>{{course.year}}</p>
        <p>{{course.id}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import "boxicons";

export default {
  name: "ClassBox",
  props: {
    courses: Array
  }
};
</script>

<style scoped>
.align {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
.bold {
  font-weight: 700;
}

.spacer {
  background-color: #edf2f9;
  width: 100%;
  height: 1px;
}
@media only screen and (max-width: 400px) {
  .shrink {
    font-size: 14px;
    padding: 5px 10px;
  }
}
</style>