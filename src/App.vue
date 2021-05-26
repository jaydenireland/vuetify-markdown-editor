<template>
  <v-app>
    <Editor
      mode="preview"
      ref="editor"
      hint="Hint"
      :outline="false"
      :renderer="renderer"
      v-model="text"
      rows="5"
    />
  </v-app>
</template>

<script>
import { Editor } from "./build-entry.js";
import { VApp } from 'vuetify/lib';
import markdownIt from 'markdown-it'

export default {
  name: "app",
  components: {
    Editor,
    VApp
  },
  data() {
    return {
      renderer: markdownIt(),
      text: "",
    };
  },
  mounted() {
    // Access properties or methods using $refs
    // this.$refs.editor.focus();
    // this.$refs.editor.upload();

    // Dark theme
    this.$vuetify.theme.dark = true;
  }
};
</script>
