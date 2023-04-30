<script lang="ts" setup>
defineProps<{
  isActive: boolean;
  socialLinks: ArticlePreviewIconProps[];
}>();
</script>

<template>
  <button
    :class="{
      'is-active': isActive,
    }"
    class="ArticlePreview-shareButton"
  >
    <div
      :class="{
        'is-active': isActive,
      }"
      class="ArticlePreview-tooltip"
      @click.stop="() => {}"
    >
      <p class="ArticlePreview-tooltipText">Share</p>
      <ArticlePreviewSocialLinks :social-links="socialLinks" />
    </div>
    <ArticlePreviewIcon
      :class="{
        'is-active': isActive,
      }"
      class="ArticlePreview-shareIcon"
      href="icon-share"
    ></ArticlePreviewIcon>
  </button>
</template>
