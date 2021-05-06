<template>
  <main>
      <div class="container-main">
          <div class="container-cards">
              <div class="cards">
                  cards
              </div>
          </div>
      </div>
  </main>
</template>

<script>
import axios from 'axios';

export default {
    name: 'Main',
    data(){
        return {
            apiURL: 'https://flynn.boolean.careers/exercises/api/array/music',
            cardsList: [],
            loading: true,
        }
    },
    created(){
        this.getCards();
    },
    methods: {
        getCards(){
            axios.get(this.apiURL)
            .then(res =>{
                this.cardsList = res.data;
                this.loading = false;
            })
            .catch(err =>{
                'Error' + err;
            });
        }
    }
}
</script>

<style scoped lang="scss">
@import '../scss/general.scss';

.container-main{
    height: 100vh;
    background: $second;
}

.container-cards{
    width: 1170px;
    display: flex;
}
</style>