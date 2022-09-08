<template>
  <div class="hello container py-3 text-center">
    <label for="genre">Choose a genre:</label>
    <select name="genre" id="tracks" class="ms-2" v-model="selected" @change="$emit('select',selected)">
      <option v-for="(option,i) in options" :value="option" :key="i">
        {{ option }}
      </option>
    </select>
    <div class="mt-2">
      <label for="artist">Choose an artist:</label>
      <select name="artist" id="artist" class="ms-2" v-model="selectedArtist" @change="$emit('selectArtist',selectedArtist)">
        <option v-for="(artist,i) in artists" :value="artist" :key="i">
          {{ artist }}
        </option>
      </select>
    </div>
  </div>
</template>
      


<script>
export default {
  name: 'MainHeader',
  props: {
    msg: String
  },
  data() {
    return {
      selectedArtist: '',
      artists: [
        '',
        'Bon Jovi',
        'Queen',
        'Sting',
        'Jazz',
        'Iron Maiden',
        'Eric Clapton',
        'Deep Purple',
        'Metallica',
        'Dave Weckl',
      ],
      selected: '',
      options: [
        '',
        'Rock',
        'Pop',
        'Jazz',
        'Metal',
      ]
    }
  }
}
</script>


<style scoped lang="scss">
@import '../styles/main.scss';

.hello {
  color: white;

}
</style>
