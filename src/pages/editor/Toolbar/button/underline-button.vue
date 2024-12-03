<script setup>
import { editor } from "../../editor.js";
import { throttle } from "lodash";

// 切换斜体
const isUnderlineActive = ref(false);
const handleChangeUnderline = () => {
  editor.chain().focus().toggleUnderline().run();
};

// 斜体状态回显
const handleUpdateUnderlineState = ({ editor }) => {
  if (editor.isActive("underline")) {
    isUnderlineActive.value = true;
  } else {
    isUnderlineActive.value = false;
  }
};
editor.on(
  "transaction",
  throttle(handleUpdateUnderlineState, 240, { leading: false }),
);
</script>

<template>
  <button
    class="underline"
    :class="{ active: isUnderlineActive }"
    @click="handleChangeUnderline"
  >
    <svg-icon name="underline"></svg-icon>
  </button>
</template>

<style lang="less" scoped></style>
