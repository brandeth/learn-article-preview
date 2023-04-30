<script lang="ts" setup>
defineProps<{
  isActive: boolean;
}>();
</script>

<template>
  <div
    :class="{
      'is-hidden': isActive,
    }"
    class="ArticlePreview-avatarContainer"
  >
    <img
      class="ArticlePreview-avatar"
      src="/avatar-michelle.jpg"
      alt="Michelle Appleton"
    />
  </div>
</template>
