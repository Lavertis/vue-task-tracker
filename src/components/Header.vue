<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
        v-show="homepage"
        :color="showAddTask?'red':'green'"
        :text="showAddTask?'Close':'Add Task'"
        @btn-click="$emit('toggle-add-task')"/>
  </header>
</template>

<script>
import Button from "@/components/Button";

export default {
  name: "Header",
  props: {
    title: String,
    showAddTask: Boolean,
  },
  components: {Button},
  computed: {
    homepage() {
      return this.$route.path === '/';
    }
  }
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>