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
  <div
    class="ArticlePreview-footer"
    :class="{
      'is-active': isActive,
    }"
    @click.stop="() => {}"
  >
    <ArticlePreviewAvatar :is-active="isActive" />
    <div class="ArticlePreview-detailsContainer">
      <div
        :class="{
          'is-hidden': isActive,
        }"
      >
        <p class="ArticlePreview-author">Michelle Appleton</p>
        <p class="ArticlePreview-date">28 Jun 2020</p>
      </div>
      <p
        :class="{
          'is-hidden': !isActive,
        }"
        class="ArticlePreview-shareText"
      >
        Share
      </p>
      <ArticlePreviewSocialLinks
        :class="{
          'is-hidden': !isActive,
        }"
        :social-links="socialLinks"
      />
    </div>
    <ArticlePreviewShareButton
      @click.stop="$emit('toggleShareMenu')"
      :is-active="isActive"
      :social-links="socialLinks"
    />
  </div>
</template>
