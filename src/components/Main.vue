<template>
  <main>
      <div class="container-main">
          <div class="container-cards">
              <div v-for="(card, index) in cardsList" :key="index" class="cards">
                  <Cards />
              </div>
          </div>
      </div>
  </main>
</template>

<script>
import axios from 'axios';
import Cards from '@/components/Cards.vue';


export default {
    name: 'Main',
    components: {
        Cards,
    },
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
    margin: 0 auto;
    width: 1170px;
    display: flex;
}
</style>