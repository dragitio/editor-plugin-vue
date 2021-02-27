<template>
  <div id="app">
    <dragit-editor :options="options" style="height: 100vh" />
  </div>
</template>

<script>
import Vue from "vue";
import DragitEditor from "@/dragit-editor.vue";

export default Vue.extend({
  name: "ServeDev",
  components: {
    DragitEditor,
  },
  computed: {
    options() {
      return {
        id: "dragit-editor-plugin",
        apiKey: '1d5cb5ba-5a13-4acf-9f32-dc9239063f9e',
        callbacks: {},
      };
    },
  },
});
</script>

<style>
body {
  margin: 0;
}
</style>