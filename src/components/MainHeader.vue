<template>
  <div class="hello container py-3 text-center">
    <label for="genre">Choose a genre:</label>
    <select name="genre" id="tracks" class="ms-2" v-model="selected">
      <option disabled value="">Select a genre</option>
      <option 
        v-for="(option,i) in options" 
        :value="selected"
        :key="i"
      >
          {{ option }}
      </option>
      <!-- <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option> -->
    </select>
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
      selected: '',
      options: [
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
