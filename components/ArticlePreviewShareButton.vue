<script lang="ts" setup>
defineProps<{
  isActive: boolean;
}>();
</script>

<template>
  <button
    :class="{
      'is-active': isActive,
    }"
    class="ArticlePreview-shareButton"
  >
    <ArticlePreviewIcon
      :class="{
        'is-active': isActive,
      }"
      class="ArticlePreview-shareIcon"
      href="icon-share"
    ></ArticlePreviewIcon>
  </button>
</template>
