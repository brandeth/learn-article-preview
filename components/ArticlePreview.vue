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
    <div class="ArticlePreview-imageContainer">
      <img class="ArticlePreview-image" src="/drawers.jpg" alt="Drawers" />
    </div>
    <div class="ArticlePreview-contentContainer">
      <ArticlePreviewOverview />
      <div
        class="ArticlePreview-footer"
        :class="{
          'is-active': isActive,
        }"
      >
        <ArticlePreviewAvatar :is-active="isActive" />
        <div class="ArticlePreview-detailsContainer">
          <template v-if="!isActive">
            <p class="ArticlePreview-author">Michelle Appleton</p>
            <p class="ArticlePreview-date">28 Jun 2020</p>
          </template>
          <ArticlePreviewSocialLinks v-else :social-links="socialLinks" />
        </div>
        <ArticlePreviewShareButton
          @click="toggleShareMenu"
          :is-active="isActive"
        />
      </div>
    </div>
  </div>
</template>
