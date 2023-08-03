<template>
  <div class="course">
    <p>Id: {{ course.id }}</p>
    <p>Name: {{ course.name }}</p>
    <p>Description: {{ course.description }}</p>
    <p>Hours: {{ course.hours }}</p>
    <p>Students: {{ course.students }}</p>
    <!-- <button v-if="button === 0 && course.students <= 20" @click="outerAdd">Add course</button> -->
    <!-- <button v-if="button === 0" @click="outerAdd">Add course</button> -->
    <button v-if="course.students >= 20" disabled>Completed</button>
    <button v-else-if="button === 0" @click="outerAdd">Add course</button>
    <button v-else @click="outerDelete">Remove course</button>
  </div>
</template>

<script>
export default {
  name: "CourseItem",
  data() {
    return {
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
