<template>
    <div class="container">
        <div class="row gap-3">
            <div class="card col-5" style="width: 18rem;" v-for="(card,i) in cardList" :key="i">
                <img 
                    :src="card.poster" 
                    class="card-img-top" 
                    alt="...">
                <div class="card-body">
                    <h5 class="card-title">{{cardList.title}}</h5>
                    <p class="card-text">{{card.author}}</p>

                </div>
            </div>
        </div>



    </div>
</template>

<script>
import axios from "axios"

export default {
    name: 'MainContent',
    data() {
        return {
            cardList: []
        }
    },
    created() {
        axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((res) => {
                console.log(res.data)
                this.cardList = res.data
            })
            .finally(() => {
                console.log(this.cardList)
            })
    }
}
</script>

<style lang="scss" scoped>
@import '../styles/variables.scss';

* {
    font-family: $main-font-family;
}
</style>