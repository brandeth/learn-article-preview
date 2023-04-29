<script lang="ts" setup>
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
    <div class="ArticlePreview-content">
      <h3 class="ArticlePreview-title">
        Shift the overall look and feel by adding these wonderful touches to
        furniture in your home
      </h3>
      <p class="ArticlePreview-body">
        Ever been in a room and felt like something was missing? Perhaps it felt
        slightly bare and uninviting. I've got some simple tips to help you make
        any room feel complete.
      </p>
    </div>
    <div
      class="ArticlePreview-footer"
      :class="{
        'is-active': isActive,
      }"
    >
      <div class="ArticlePreview-avatarContainer">
        <img
          v-if="!isActive"
          class="ArticlePreview-avatar"
          src="/avatar-michelle.jpg"
          alt="Michelle Appleton"
        />
        <p v-else>Share</p>
      </div>
      <div class="ArticlePreview-detailsContainer">
        <template v-if="!isActive">
          <p class="ArticlePreview-author">Michelle Appleton</p>
          <p class="ArticlePreview-date">28 Jun 2020</p>
        </template>
        <div v-else class="ArticlePreview-socialLinks">
          <a href="#">
            <ArticlePreviewIcon
              href="icon-facebook"
              :width="20"
              :height="20"
            ></ArticlePreviewIcon>
          </a>
          <a href="#">
            <ArticlePreviewIcon
              href="icon-twitter"
              :width="20"
              :height="17"
            ></ArticlePreviewIcon>
          </a>
          <a href="#">
            <ArticlePreviewIcon
              href="icon-pinterest"
              :width="20"
              :height="20"
            ></ArticlePreviewIcon>
          </a>
        </div>
      </div>
      <button
        @click="toggleShareMenu"
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
    </div>
  </div>
</template>
