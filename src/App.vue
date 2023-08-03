<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <p>{{ count }}</p>
  <div class="groupe-courses">
    <CourseItem
      v-for="course in courses"
      :course="course"
      :key="course.id"
      @count-to-parent="addOne"
      @delete-to-parent="deleteOne"
    ></CourseItem>
  </div>
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
          students: "14",
        },
        {
          id: 2,
          name: "Framework",
          description: "Winter course",
          hours: "20",
          students: "20",
        },
        {
          id: 3,
          name: "Wordpress",
          description: "Fall course",
          hours: "16",
          students: "2",
        },
        {
          id: 4,
          name: "React",
          description: "Summer course",
          hours: "54",
          students: "0",
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
    deleteOne() {
      this.count--;
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
.course {
  border: 1px solid #cacaca;
  margin-bottom: 20px;
}
</style>
