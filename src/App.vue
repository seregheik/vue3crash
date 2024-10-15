<template>
  <h1>DC HEROES : {{ herosCount }}</h1>
  <h3>{{ fullname }}</h3>
  <ul>
    <li v-for="(hero, key) in dcHeroes" v-bind:key="key">{{ hero.name }}</li>
  </ul>

  <form @submit.prevent="addHero">
    <input v-model.lazy.trim="newHero" placeholder="enter hero name" />
    <button type="submit">Add Hero</button> <br> <br>
    <button></button>
  </form>
</template>

<script>
export default {
  computed: {
    herosCount() {
      return this.dcHeroes.length;
    },
    fullname: {
      get() {
        return `${this.fname} ${this.lname}`;
      },
      set(fullname) {
        alert('fullname has changed ');
        [this.fname, this.lname] = fullname.split(' ');
      }
    },
  },
  data() {
    return {
      isActive: false,
      fname: 'Osasere',
      lname: 'Ikponmwosa',
      newHero: '',
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
        this.dcHeroes.push({ name: this.newHero });
        this.newHero = '';

      }
    }
  },
}
</script>
