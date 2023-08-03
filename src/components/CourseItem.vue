<template>
  <!-- <h2>Course</h2> -->
  <!-- <p>{{ count }}</p> -->

  <!-- <button @click="innerAdd">Add</button> -->
  <p>{{ course.id }}</p>
  <p>{{ course.name }}</p>
  <p>{{ course.description }}</p>
  <p>{{ course.hours }}</p>

  <button v-if="button == 0" @click="outerAdd">Add course</button>
  <button v-else @click="outerDelete">Remove course</button>
</template>

<script>
export default {
  name: "CourseItem",
  data() {
    return {
      count: 0,
      button: 0,
    };
  },
  props: {
    course: {
      type: Array,
      required: true,
    },
  },
  methods: {
    // innerAdd() {
    //   this.count++;
    // },
    outerAdd() {
      this.$emit("count-to-parent");
      this.button = 1;
    },
    outerDelete() {
      this.$emit("delete-to-parent");
      this.button = 0;
    },
  },
};
</script>
