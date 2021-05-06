<template>
  <header>
      <div class="logo-container">
          <img src="@/assets/logo.png" alt="spotify-logo">
      </div>
  </header>
</template>

<script>
export default {
    name:'Header',
}
</script>

<style scoped lang="scss">
@import './scss/general.scss';


.logo-container{
    height: 80px;
    background: #000;
    display: flex;
    align-items: center;
}

.logo-container img{
    width: 50px;
    margin-left: 1rem;
}
</style>

