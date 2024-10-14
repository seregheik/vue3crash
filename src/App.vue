<template>
  <h1>DC HEROES</h1>
  <ul>
    <li v-for="(hero, key) in dcHeroes" v-bind:key="key">
      {{ hero }} {{ key }}
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      dcHeroes: ['Superman', 'Batman', 'Wonderwoman', 'Supergirl'],
    }
  },
}
</script>
