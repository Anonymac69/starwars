<template>
  <div>

    <character :data='character' :single='true' />

  </div>
</template>

<script>
export default {
  async asyncData({ $axios, route}) {
    const id = route.params.id;
    const endpoint = `/people/${id}`;
    const character = await $axios.$get(endpoint);
    return { character }
  }
}
</script>

<style>

</style>