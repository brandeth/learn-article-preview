<script lang="ts" setup>
const socialLinks = ref<ArticlePreviewIconProps[]>([
  {
    href: "icon-facebook",
    width: 20,
    height: 20,
    to: "https://www.facebook.com/frontendmentor/",
  },
  {
    href: "icon-twitter",
    width: 20,
    height: 17,
    to: "https://twitter.com/frontendmentor?lang=en",
  },
  {
    href: "icon-pinterest",
    width: 20,
    height: 20,
    to: "https://www.pinterest.ph/pin/736901557779895445/",
  },
]);

const isActive = ref(false);

const toggleShareMenu = () => {
  isActive.value = !isActive.value;
};
</script>

<template>
  <div class="ArticlePreview">
    <ArticlePreviewImage />
    <ArticlePreviewContent
      @toggle-share-menu="toggleShareMenu"
      :is-active="isActive"
      :social-links="socialLinks"
    />
  </div>
</template>
