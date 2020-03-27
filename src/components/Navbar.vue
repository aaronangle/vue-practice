<template>
  <div class="navbar">
    <img src="../assets/Capture-removebg-preview.png" alt="Gila Hank Logo" class="logo" />
    <div class="nav-items">
      <div class="drop1">
        <h3 class="nav-button">
          Registration & Classes
          <box-icon name="down-arrow" color="white" type="solid" size="xs"></box-icon>
        </h3>
        <div class="dropdown drop1-content">
          <h3>My Schedule</h3>
          <h3>Registration</h3>
          <h3>Grades</h3>
          <h3>Advising & Course Completion</h3>
          <h3>Course Evaluation</h3>
        </div>
      </div>
      <div class="drop2">
        <h3 class="nav-button">
          Accounts & Documents
          <box-icon name="down-arrow" color="white" type="solid" size="xs"></box-icon>
        </h3>
        <div class="dropdown drop2-content">
          <h3>My Account</h3>
          <h3>Transcripts</h3>
          <h3>Upload Documents</h3>
          <h3>Petitions</h3>
          <h3>Placement Scores</h3>
          <h3>Feedback</h3>
        </div>
      </div>
      <div class="drop3">
        <h3 class="nav-button">
          Financial
          <box-icon name="down-arrow" color="white" type="solid" size="xs"></box-icon>
        </h3>
        <div class="dropdown drop3-content">
          <h3>Pay</h3>
          <h3>Financial Aid</h3>
          <h3>Scholarships</h3>
          <h3>Waivers</h3>
          <h3>Account Balance & Tax Forms</h3>
        </div>
      </div>
      <h3 class="nav-button">Dorm & Meal Plan</h3>
    </div>
    <div class="user">
      <p>Welcome {{user}}</p>
      <div class="drop4">
        <box-icon name="user-rectangle" type="solid" color="#ffffff" size="lg"></box-icon>
        <div class="signout drop4-content">
          <h3>Logout</h3>
        </div>
      </div>
    </div>
    <div class="menu" v-on:click="openMenu">
      <box-icon name="menu" type="solid" color="#ffffff" size="lg"></box-icon>
    </div>
    <div class="shadow" :style="display" v-on:click="closeMenu"></div>
    <div class="sidenav scrollbar" :style="width">
      <div class="close">
        <box-icon name="x-circle" color="#330066" size="lg" v-on:click="closeMenu" class="hover"></box-icon>
      </div>
      <h3 class="main" v-on:click="setOpacity(1)">
        <box-icon name="pencil" color="#330066"></box-icon>Registration & Classes
        <box-icon name="down-arrow" color="#330066" type="solid" size="xs"></box-icon>
      </h3>
      <div class="sidedrop" :style="opacity1">
        <h3>My Schedule</h3>
        <h3>Registration</h3>
        <h3>Grades</h3>
        <h3>Advising & Course Completion</h3>
        <h3>Course Evaluation</h3>
      </div>
      <h3 class="main" v-on:click="setOpacity(2)">
        <box-icon name="note" color="#330066"></box-icon>Account & Documents
        <box-icon name="down-arrow" color="#330066" type="solid" size="xs"></box-icon>
      </h3>
      <div class="sidedrop" :style="opacity2">
        <h3>My Account</h3>
        <h3>Transcripts</h3>
        <h3>Upload Documents</h3>
        <h3>Petitions</h3>
        <h3>Placement Scores</h3>
        <h3>Feedback</h3>
      </div>
      <h3 class="main" v-on:click="setOpacity(3)">
        <box-icon name="dollar-circle" color="#330066"></box-icon>Financial
        <box-icon name="down-arrow" color="#330066" type="solid" size="xs"></box-icon>
      </h3>
      <div class="sidedrop" :style="opacity3">
        <h3>Pay</h3>
        <h3>Financial Aid</h3>
        <h3>Scholarships</h3>
        <h3>Waivers</h3>
        <h3>Account Balance & Tax Forms</h3>
      </div>
      <h3 class="main">
        <box-icon name="building-house" color="#330066"></box-icon>Dorm & MealPlan
      </h3>
      <h3 class="main">
        <box-icon name="user" color="#330066"></box-icon>Logout
      </h3>
    </div>
  </div>
</template>

<script>
import "boxicons";

export default {
  name: "Navbar",
  props: {
    user: String
  },
  data() {
    return {
      width: "width: 0px",
      display: "display: none",
      opacity1: "opacity: 0; height: 0px; margin: 0",
      opacity2: "opacity: 0; height: 0px; margin: 0",
      opacity3: "opacity: 0; height: 0px; margin: 0",
      clicked1: false,
      clicked2: false,
      clicked3: false
    };
  },
  methods: {
    closeMenu() {
      this.width = "width: 0px";
      this.display = "display: none";
    },
    openMenu() {
      this.width = "width: 300px";
      this.display = "display: block";
    },
    setOpacity(num) {
      if (num === 1) {
        if (this.clicked1) {
          this.opacity1 = "opacity: 0; height: 0px";
          this.clicked1 = false;
        } else {
          this.opacity1 = "opacity: 1; height: 200px";
          this.clicked1 = true;
        }
      } else if (num === 2) {
        if (this.clicked2) {
          this.opacity2 = "opacity: 0; height: 0px";
          this.clicked2 = false;
        } else {
          this.opacity2 = "opacity: 1; height: 200px";
          this.clicked2 = true;
        }
      } else {
        if (this.clicked3) {
          this.opacity3 = "opacity: 0; height: 0px";
          this.clicked3 = false;
        } else {
          this.opacity3 = "opacity: 1; height: 200px";
          this.clicked3 = true;
        }
      }
    }
  }
};
</script>

<style scoped>
* {
  color: white;
}
.dropdown {
  display: none;
  color: black;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  padding: 12px 16px;
  z-index: 1;
  border-radius: 5px;
}
.signout {
  display: none;
  color: black;
  position: absolute;
  background-color: #f9f9f9;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  padding: 12px 16px;
  z-index: 1;
  border-radius: 5px;
}
.drop1:hover .drop1-content {
  display: block;
}
.drop2:hover .drop2-content {
  display: block;
}
.drop3:hover .drop3-content {
  display: block;
}
.drop4:hover .drop4-content {
  display: block;
}
.navbar {
  background-color: #330066;
  height: 90px;
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  margin-bottom: 20px;
  max-width: 100vw;
}
.logo {
  background-color: #eeeff0;
  border-radius: 10px;
}
.nav-items h3 {
  color: rgba(255, 255, 255, 0.9);
  margin: 0;
}
.dropdown h3,
.sidedrop h3 {
  color: #330066;
  margin: 10px;
  border-bottom: solid 1px #edf2f9;
  transition: 0.5s;
}
.dropdown h3:hover,
.sidedrop h3:hover {
  border-bottom: solid 1px #330066;
}
.sidedrop h3 {
  position: relative;
  z-index: 1;
}
.sidedrop {
  margin-left: 40px;
}
.signout h3 {
  color: #330066;
  margin: 0;
}
.nav-items {
  align-self: flex-end;
  margin: 10px;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: flex-end;
  width: 60%;
}
.user {
  display: flex;
  justify-content: center;
  align-items: center;
}
.user:hover {
  cursor: pointer;
}
h3:hover {
  cursor: pointer;
}
.menu {
  display: none;
}
.menu:hover {
  cursor: pointer;
}
.sidenav {
  background-color: #f9f9f9;
  z-index: 30;
  position: fixed;
  height: 100%;
  right: 0;
  top: 0;
  width: 300px;
  transition: 0.3s;
  overflow: scroll;
  overflow-x: hidden;
}
.sidenav h3 {
  color: #330066;
}
.shadow {
  background-color: #222222;
  opacity: 0.4;
  z-index: 1;
  position: fixed;
  height: 100%;
  left: 0;
  top: 0;
  width: 100%;
}
.sidedrop {
  transition: 0.3s;
}
.main {
  position: relative;
  z-index: 10;
}
.close {
  display: flex;
  justify-content: flex-end;
}

@media only screen and (max-width: 1300px) {
  .nav-button {
    font-size: 16px;
  }
}
@media only screen and (max-width: 1150px) {
  .menu {
    display: block;
    margin-right: 40px;
  }
  .logo {
    margin-left: 40px;
  }
  .user,
  .nav-items {
    display: none;
  }
  .navbar {
    justify-content: space-between;
  }
}
</style>