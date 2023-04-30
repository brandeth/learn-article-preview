<script lang="ts" setup>
defineProps<{
  socialLinks: ArticlePreviewIconProps[];
}>();
</script>

<template>
  <div class="ArticlePreview-socialLinks">
    <a v-for="(link, index) in socialLinks" :key="index" :href="link.to">
      <ArticlePreviewIcon
        :href="link.href"
        :width="link.width"
        :height="link.height"
      ></ArticlePreviewIcon>
    </a>
  </div>
</template>
