<template>
  <div class="hello container py-3 text-center">
    <label for="genre">Choose a genre:</label>
    <select name="genre" id="tracks" class="ms-2">
      <option value="..."></option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'MainHeader',
  props: {
    msg: String
  }
}
</script>


<style scoped lang="scss">
@import '../styles/main.scss';

.hello {
  color: white;
  
}
</style>
