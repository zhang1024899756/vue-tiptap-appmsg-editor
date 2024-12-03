<script setup>
import "@/assets/styles/tiptap-appmsg.css";
// import FunctionBar from "./FunctionBar/functionBar.vue";
import Toolbar from "./Toolbar/toolbar.vue";
// import Sidebar from "./Sidebar/sidebar.vue";
import { editor } from "./editor.js";

const editorContainerRef = ref();
onMounted(() => {
  editorContainerRef.value.insertBefore(
    editor.options.element,
    editorContainerRef.value.querySelector(".footer"),
  );
});
</script>

<template>
  <div class="editor-wrapper">
    <toolbar />
    <div ref="editorContainerRef" class="editor-container"></div>
  </div>
</template>

<style lang="less" scoped>
/* 编辑器 */
.editor-wrapper {
  height: 100%;
}

.editor-container {
  position: relative;
  margin: 0 auto;
  z-index: 1;
  :deep(.tiptap-editor) {
    padding: 30px 30px 115px;
    position: relative;
    border-radius: 6px;
    background-color: #fff;
    box-shadow: 0 1px 5px 0 rgba(0, 0, 0, 0.05);
  }
}
</style>

<style lang="less">
.modal {
  .modal-dialog {
    width: 560px;
  }

  .tabs-nav {
    display: flex;
    margin-bottom: 24px;
    border-bottom: 1px solid #eee;
  }

  .tab-item {
    padding: 4px;
    margin-bottom: -1px;
    border-bottom: 2px solid transparent;
    cursor: pointer;
  }

  .tab-item.active {
    border-bottom-color: #07c160;
  }

  .tab-item + .tab-item {
    margin-left: 12px;
  }

  .form-item {
    margin-bottom: 15px;
  }

  .form-item label {
    display: inline-block;
    min-width: 102px;
    margin-right: 12px;
    text-align: right;
  }

  input[type="text"] {
    width: 320px;
    height: 32px;
    padding: 6px 12px;
    border-radius: 4px;
    border: 1px solid #eee;
  }

  input[type="text"]:focus {
    border-color: #07c160;
  }
}
</style>
