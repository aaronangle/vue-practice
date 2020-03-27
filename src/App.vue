<template>
  <div id="app">
    <Navbar user="Aaron" />
    <Home />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Home from "./pages/Home.vue";

export default {
  name: "App",
  components: {
    Navbar,
    Home
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  font-family: Poppins, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji",
    "Segoe UI Symbol";
}
html body {
  margin: 0;
  padding: 0;
  max-width: 100vw;
  background-color: #edf2f9;
}
.button-primary {
  color: white;
  font-size: 16px;
  border: none;
  background-color: #330066;
  border-radius: 10px;
  padding: 10px 20px;
  margin: 5px;
  box-shadow: 0 0 0 1px rgba(43, 45, 80, 0.1),
    0 2px 5px 0 rgba(43, 45, 80, 0.08), 0 1px 1.5px 0 rgba(0, 0, 0, 0.07),
    0 1px 2px 0 rgba(0, 0, 0, 0.08);
  transition: 0.3s;
  border: solid 1px #330066;
}
.button-primary:hover {
  cursor: pointer;
  background-color: white;
  color: #330066;
  border: solid 1px #330066;
}
.button-secondary {
  color: #330066;
  font-size: 16px;
  border: solid 1px #330066;
  background-color: white;
  border-radius: 10px;
  padding: 10px 20px;
  box-shadow: 0 0 0 1px rgba(43, 45, 80, 0.1),
    0 2px 5px 0 rgba(43, 45, 80, 0.08), 0 1px 1.5px 0 rgba(0, 0, 0, 0.07),
    0 1px 2px 0 rgba(0, 0, 0, 0.08);
  transition: 0.5s;
  text-shadow: 1px 1px rgba(0, 0, 0, 0.25);
}
.primary {
  color: #330066;
}
.secondary {
  color: #4b5664;
}
.light {
  color: #f9fafd;
}
.button-secondary:hover {
  cursor: pointer;
  background-color: #330066;
  color: white;
}
.bg-primary {
  background-color: #330066;
}
.bg-light {
  background-color: #f9fafd;
}
.box-lg {
  width: 50vw;
}
.box-sm {
  width: 40vw;
}
.box {
  background-color: white;
  margin: 20px;
  border-radius: 10px;
  box-shadow: 0 7px 14px 0 rgba(65, 69, 88, 0.1),
    0 3px 6px 0 rgba(0, 0, 0, 0.07);
}
.header {
  height: 50px;
  padding: 0 40px;
  background-color: #f9fafd;
  color: white;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  border-radius: 10px 10px 0 0;
}
.flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}
.flex-center-col {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.flex-center-row {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.hover:hover {
  cursor: pointer;
}
.scrollbar::-webkit-scrollbar {
  width: 5px;
}
.scrollbar::-webkit-scrollbar-thumb {
  background: #888;
}
.scrollbar::-webkit-scrollbar-track {
  background: #f1f1f1;
}
.scrollbar::-webkit-scrollbar-thumb {
  background: #888;
}
.scrollbar::-webkit-scrollbar-thumb:hover {
  background: #555;
}
@media only screen and (max-width: 1000px) {
  .box {
    width: 90vw;
  }
}
@media only screen and (max-width: 400px) {
  .header {
    padding: 0 10px;
  }
}
</style>
