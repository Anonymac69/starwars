<template>
  
  <div>
    <div v-for="(character, index) in characters" :key='index'>
        <character :data='character' :id='index + 1' />
    </div>
  </div>

</template>

<script>
export default {
  async asyncData({ $axios }) {
    const endpoint = '/people';
    const { results: characters } = 
    await $axios.$get(endpoint);
    console.log(characters);
    return { characters }
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

</style>
 