<template>
  <div class="home">
    <div>{{ moneyUSD }}</div>
    <UserPhoto :name="item.name" :no="item.no" v-for="item in items"/>
    <router-link to="/about">About</router-link>
  </div>
</template>

<script>

  import UserPhoto from "../components/UserPhoto";
  import axios from "axios";

  export default {
    name: 'home',

    components: {
      UserPhoto
    },

    data() {
      return {
        items: [],
        money: 100
      }
    },

    computed: {
      moneyUSD(){
        let usd = this.money / 6.8
        usd = Math.round(usd * 100) / 100
        return usd;
      }
    },



    mounted() {
      axios.get('data.json')
          .then(
              (response) => {
                this.items = response.data;
              }
          );

      this.interval = setInterval(()=>{
        console.log(new Date())
      },1000)
    },
    beforeDestroy() {
      clearInterval(this.interval)
    }

  }
</script>
