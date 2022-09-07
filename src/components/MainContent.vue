<template>
    <div>

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
    }
}
</script>

<style lang="scss" scoped>

</style>