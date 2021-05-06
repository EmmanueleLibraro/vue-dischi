<template>
  <div class="post">
      <img :src="info.poster" :alt="info.title">
      <h1>{{ info.title}}</h1>
      <p>{{ info.author}}</p>
      <p>{{ info.genre}}</p>
      <p>{{ info.year}}</p>
  </div>
</template>

<script>
export default {
    name: 'Cards',
    props: ['info']
}
</script>

<style>
.post img{
    width: 150px;
    border-radius: 5px;
}

.post h1{
    font-size: 18px;
}
</style>