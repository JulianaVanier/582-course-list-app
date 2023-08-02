<template>
  <!-- <h2>Course</h2> -->
  <!-- <p>{{ count }}</p> -->

  <!-- <button @click="innerAdd">Add</button> -->
  <p>{{ course.id }}</p>
  <p>{{ course.name }}</p>
  <p>{{ course.description }}</p>
  <p>{{ course.hours }}</p>
  <!-- <button @click="innerAdd">Add</button> -->
  <!-- <button @click="outerAdd">Add to parent</button> -->
</template>

<script>
export default {
  name: "CourseItem",
  data() {
    return {
      count: 0,
    };
  },
  props: {
    course: {
      type: Array,
      required: true,
    },
  },
  methods: {
    innerAdd() {
      this.count++;
    },
    outerAdd() {
      this.$emit("count-to-parent");
    },
  },
};
</script>
