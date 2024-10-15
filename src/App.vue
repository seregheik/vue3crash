<template>
  <h1>DC HEROES</h1>
  <ul>
    <li v-for="(hero, key) in dcHeroes" v-bind:key="key">{{ hero.name }}</li>
  </ul>

  <form @submit.prevent="addHero">
    <input v-model.lazy.trim="newHero" placeholder="enter hero name" />
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
  methods: {
    addHero() {
      if (this.newHero != '') {
        alert(`added: ${this.newHero}`);
        this.dcHeroes.push({ name: this.newHero });
        this.newHero = '';

      }
    }
  },
}
</script>
