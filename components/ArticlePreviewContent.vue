<script lang="ts" setup>
defineProps<{
  isActive: boolean;
  socialLinks: ArticlePreviewIconProps[];
}>();

defineEmits<{
  toggleShareMenu: () => void;
}>();
</script>

<template>
  <div class="ArticlePreview-contentContainer">
    <ArticlePreviewOverview />
    <ArticlePreviewFooter
      @toggle-share-menu="$emit('toggleShareMenu')"
      :is-active="isActive"
      :social-links="socialLinks"
    />
  </div>
</template>
