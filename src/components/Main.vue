<template>
  <main>
      <div class="container-main">
          <div class="container-cards">
              <div v-for="(card, index) in cardsList" :key="index" class="cards">
                  <Cards :info = "card"/>
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
                this.cardsList = res.data.response;
                // console.log('console log', this.cardsList = res.data.response.poster);
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
    // width: 1270px;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    padding-top: 100px;
}

.cards{
    cursor: pointer;
    text-align: center;
    color: #fff;
    max-width: 200px;
    flex-basis: calc(100% / 8 );
    margin: 1rem;
    background: $back;
    border-radius: 5px;
    padding: 1rem;
}
</style>