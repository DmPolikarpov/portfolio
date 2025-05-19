<script setup>

</script>

<template>
  <div class="container">
    <div class="section-info center">
      <div class="section-info-title">I'm <span>Dmitrii Polikarpov</span></div>
      <div class="section-info-description">This is <span>Dmitrii Polikarpov</span>, a JavaScript developer and an engineer.</div>
    </div>
    <div class="section-image">
      <img src="../assets/photo.png" alt="photo" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
  .container {
    display: inline-flex;
    justify-content: space-around;
    width: 80vw;
    max-width: 1200px;
    height: 100%;
  }

  .section-info {
    color: var(--text-color);
    font-size: var(--font-size);

    .section-info-title {
      color: var(--active-color);
      font-size: var(--title-font-size);
    }

    span {
      color: var(--hovered-color);
    }

  }

  .section-image {

    display: flex;
    align-items: flex-end;

    img {
      max-height: 80vh;
    }
  }
</style>
