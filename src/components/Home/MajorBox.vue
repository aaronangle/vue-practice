<template>
  <div class="box box-sm">
    <div class="header">
      <box-icon name="line-chart" type="solid" color="#330066" size="lg"></box-icon>
      <button class="button-primary">Update Major</button>
    </div>
    <div class="flex-center-col">
      <h3 class="secondary">Declared Major: Accounting</h3>
      <Progress
        :transitionDuration="1500"
        :radius="55"
        :strokeWidth="10"
        strokeColor="#330066"
        value="46.34"
      >
        <div class="content">30.00 of 64 Credits</div>
      </Progress>
      <button class="button-primary">Run Degree Audit</button>
    </div>
  </div>
</template>

<script>
import "boxicons";
import Progress from "easy-circular-progress";
export default {
  name: "MajorBox",
  components: {
    Progress
  }
};
</script>

<style scoped>
</style>