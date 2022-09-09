<template>
    <div class="container">
        <div class="row gap-3">
            <div class="card col-2" v-for="(card,i) in filteredTracks" :key="i">
                <img :src="card.poster" class="card-img-top" :alt="card.author">
                <div class="card-body">
                    <h5 class="card-title">
                        {{card.title}}
                    </h5>
                    <p class="card-text">
                        {{card.author}} <br>
                        {{card.year}}
                    </p>
                </div>

            </div>
        </div>



    </div>
</template>
<script>
import axios from "axios"

export default {
    name: 'MainContent',
    props: {
        selected: {
            type: String,
            default: '',
        },
        selectedArtist: {
            type: String,
            default: '',
        },
    },
    data() {
        return {
            cardList: [],
        }
    },
    computed: {
        filteredTracks() {
            return this.cardList.filter((el) => {
                const genre = el.genre.toLowerCase()
                const find = this.selected.toLowerCase()
                const artist = el.author.toLowerCase()
                const artistSel = this.selectedArtist.toLowerCase()
                if (genre.includes(find) && artist.includes(artistSel)) {
                    return true
                }
                return false
            })
        }
    },


    created() {
        axios
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((res) => {
                console.log(res.data)
                this.cardList = res.data.response
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

.container {
    .row {
        .card {
            background-color: $card-bg-color;
            color: white;
            text-align: center;

            img {
                padding: 10px;
            }

            .card-title {
                font-weight: bold;
                text-transform: uppercase;
                font-size: 1.05rem;
            }

            .card-text {
                color: grey;
                padding-top: 10px;
            }
        }

    }
}
</style>
