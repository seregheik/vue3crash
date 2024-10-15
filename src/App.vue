<template>
  <h1>DC HEROES</h1>
  <ul>
    <li v-for="(hero, key) in dcHeroes" v-bind:key="key">
      {{ key }} {{ hero.name }}
    </li>
  </ul>
  <input v-model.lazy.trim="newHero" />
  <form @submit.prevent="dcHeroes[2].name = newHero">
    <button type="submit">Add Hero</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
      newHero: 'Aquaman',
      dcHeroes: [
        { name: 'Superman' },
        { name: 'Batman' },
        { name: 'Wonderwoman' },
        { name: 'Supergirl' },
      ],
    }
  },
}
</script>
