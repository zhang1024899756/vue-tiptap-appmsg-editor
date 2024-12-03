<script setup>
import { editor } from "../../editor.js";
</script>

<template>
  <button class="redo" @click="editor.commands.redo">
    <svg-icon name="redo"></svg-icon>
  </button>
</template>

<style lang="less" scoped></style>
