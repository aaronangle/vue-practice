<template>
  <div>
    <div class="two-col">
      <NotificationBox
        :users="users"
        sender="Mr. Smith"
        messages="Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
      />
      <ClassBox :courses="courses" class="courses" />
    </div>
    <div class="two-col line-up">
      <QuickLinks />
      <MajorBox />
    </div>
  </div>
</template>

<script>
import NotificationBox from "../components/Home/NotificationBox.vue";
import ClassBox from "../components/Home/ClassBox.vue";
import QuickLinks from "../components/Home/QuickLinks.vue";
import MajorBox from "../components/Home/MajorBox.vue";

import axios from "axios";

export default {
  name: "Home",
  components: {
    NotificationBox,
    ClassBox,
    QuickLinks,
    MajorBox
  },
  data() {
    return {
      url: "https://reqres.in/api/users",
      users: {},
      courses: []
    };
  },
  created: function() {
    this.fetchData();
  },
  methods: {
    fetchData() {
      axios
        .get(`${this.url}`)
        .then(res => {
          return res.data;
        })
        .then(res => {
          this.users = res;
        });
      axios.get("https://reqres.in/api/unkown").then(res => {
        this.courses = res.data.data;
      });
    },
    setResults(results) {
      this.users = results;
    }
  }
};
</script>

<style scoped>
.two-col {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.courses {
  align-self: flex-start;
}
.line-up {
  align-items: center;
}
@media only screen and (max-width: 1000px) {
  .two-col {
    flex-direction: column;
    align-items: center;
  }
  .line-up {
    flex-direction: column-reverse;
  }
  .courses {
    align-self: center;
  }
}
</style>