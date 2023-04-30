<script lang="ts" setup>
defineProps<{
  isActive: boolean;
}>();
</script>

<template>
  <div class="ArticlePreview-avatarContainer">
    <img
      v-if="!isActive"
      class="ArticlePreview-avatar"
      src="/avatar-michelle.jpg"
      alt="Michelle Appleton"
    />
    <p v-else>Share</p>
  </div>
</template>
