<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <p>{{ count }}</p>
  <p>
    <CourseItem
      v-for="course in courses"
      :course="course"
      :key="course.id"
    ></CourseItem>
  </p>
  <button @click="addOne">Add to parent</button>
  <!-- <CourseItem @count-to-parent="addOne" /> -->
  <!-- <CourseItem v-for="course in courses" :key="course"></CourseItem> -->
</template>

<script>
import CourseItem from "./components/CourseItem.vue";
// import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  data() {
    return {
      count: 0,
      courses: [
        {
          id: 1,
          name: "Web Adv Tech",
          description: "Summer course",
          hours: "25",
          student: "",
        },
        {
          id: 2,
          name: "Framework",
          description: "Winter course",
          hours: "20",
          student: "",
        },
        {
          id: 3,
          name: "Wordpress",
          description: "Fall course",
          hours: "16",
          student: "",
        },
        {
          id: 4,
          name: "React",
          description: "Summer course",
          hours: "54",
          student: "",
        },
      ],
    };
  },
  components: {
    // HelloWorld,
    CourseItem,
  },
  methods: {
    addOne() {
      this.count++;
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
