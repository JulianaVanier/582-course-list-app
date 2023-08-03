<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <h1>Selected courses: {{ count }}</h1>
  <div class="container">
    <div class="groupe-courses">
      <CourseItem
        v-for="course in courses"
        :course="course"
        :key="course.id"
        @count-to-parent="addOne(course)"
        @delete-to-parent="deleteOne(course)"
      ></CourseItem>
    </div>
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
        {
          id: 1,
          name: "Web Adv Tech",
          description: "Summer course",
          hours: "25",
          students: "14",
        },
      ],
    };
  },
  components: {
    // HelloWorld,
    CourseItem,
  },
  methods: {
    addOne(course) {
      // console.log(course);
      this.count++;
      course.students++;
    },
    deleteOne(course) {
      this.count--;
      course.students--;
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700;900&family=Poppins:wght@200;400;500;600;700;800&display=swap");

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  // margin-top: 60px;
}
h1 {
  margin-bottom: 3rem;
}

.course {
  // border: 1px solid #cacaca;
  border-radius: 8px;
  margin-bottom: 20px;
  padding: 1rem;
  width: 10rem;
  height: 17rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  box-shadow: 0px 1px 14px 7px rgba(3, 74, 40, 0.15);
}
.course h4 {
  color: #35495e;
  letter-spacing: 0.5;
}
.course p {
  font-family: "Poppins", sans-serif;
  font-size: 13px;
}
.groupe-courses {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  align-items: center;
  justify-content: center;
  margin-bottom: 6rem;
}
.container {
  max-width: 1200px;
  width: 90%;
  margin: 0 auto;
}

.button-add,
.button-completed,
.button-remove {
  margin-top: 10px;
  border-radius: 5px;
  font-family: "Poppins", sans-serif;
  cursor: pointer;
  padding: 5px 7px;
}

.button-add {
  background-color: rgb(126, 236, 126);
  border: none;
}
.button-add:hover {
  background-color: #cacaca;
}
.button-completed {
  border: 1px solid #cacaca;
  color: red;
}

.button-remove {
  background-color: rgb(248, 130, 130);
  border: none;
}
</style>
