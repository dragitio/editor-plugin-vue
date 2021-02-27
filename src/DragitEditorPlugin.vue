<template>
  <div
    id="dragit-editor-plugin"
    style="width: 100%; height: 100%; position: relative"
  ></div>
</template>

<script>
import loadScript from "load-script";

const DRAGIT_EDITOR_LOADER_URL =
  "https://cdn.dragit.io/public/dragit-editor/build/loader.js";

const DEFAULT_OPTIONS = {};

export default /*#__PURE__*/ {
  name: "DragitEditorPlugin", // vue component name
  props: {
    apiKey: {
      default: "",
      type: String,
    },
    options: {
      default: undefined,
      type: Object,
    },
  },
  data() {
    return {
      loaded: false,
    };
  },
  mounted() {
    loadScript(DRAGIT_EDITOR_LOADER_URL, { async: false }, (err) => {
      if (err) {
        throw new Error("Dragit Editor Plugin could not be loaded");
      }
      this.loaded = true;
      this.$nextTick(() => {
        this.init();
      });
    });
  },
  computed: {},
  methods: {
    init() {
      Dragit.init(
        Object.assign({}, DEFAULT_OPTIONS, this.options, {
          id: "dragit-editor-plugin",
        })
      );
    },
    load(json) {
      Dragit.load(json);
    },
  },
  destroyed() {
    if (Dragit) {
      Dragit.destroy();
    }
  },
};
</script>

<style scoped>
.dragit-editor {
  display: block;
  width: 400px;
  margin: 25px auto;
  border: 1px solid #ccc;
  background: #eaeaea;
  text-align: center;
  padding: 25px;
}
.dragit-editor p {
  margin: 0 0 1em;
}
</style>
