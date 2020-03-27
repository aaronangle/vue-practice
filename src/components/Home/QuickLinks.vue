<template>
  <div class="container flex-center-row box box-lg">
    <div class="box1 flex-center-row">
      <img src="../../assets/monstermail.png" alt="Monster Mail" />
    </div>
    <div class="box1 flex-center">
      <img src="../../assets/canvas.png" alt="Canvas" />
    </div>
    <div class="box1 flex-center">
      <h1>EAC.edu</h1>
    </div>
  </div>
</template>

<script>
import "boxicons";

export default {
  name: "QuickLinks",
  props: {
    name: String
  }
};
</script>

<style scoped>
.container {
  min-height: 150px;
  justify-content: space-evenly;
  margin-bottom: 40px;
}
.box1 {
  width: 300px;
  min-height: 150px;
  border-radius: 10px;
}
.box1:hover {
  background-color: #f9fafd;
  cursor: pointer;
}
h1 {
  color: #5d3c8e;
  margin: 0;
}
@media only screen and (max-width: 500px) {
  .box1 img {
    width: 100px;
  }
  .box1 h1 {
    max-width: 100px;
    font-size: 24px;
  }
}
</style>