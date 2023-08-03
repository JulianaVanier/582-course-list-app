<template>
  <div class="course">
    <!-- <p>Id: {{ course.id }}</p> -->
    <h4>{{ course.name }}</h4>
    <p>Description: {{ course.description }}</p>
    <p>Hours: {{ course.hours }}</p>
    <p>Students: {{ course.students }}</p>
    <progress
      id="file"
      max="20"
      :value="parseInt(course.students) + add"
    ></progress>
    <button v-if="course.students >= 20" disabled class="button-completed">
      Completed
    </button>
    <button v-else-if="button === 0" @click="outerAdd" class="button-add">
      Add course
    </button>
    <button v-else @click="outerDelete" class="button-remove">
      Remove course
    </button>
  </div>
</template>

<script>
export default {
  name: "CourseItem",
  data() {
    return {
      button: 0,
      add: 0,
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
      this.add++;
    },
    outerDelete() {
      this.$emit("delete-to-parent");
      this.button = 0;
      this.add--;
    },
  },
};
</script>
