<template>
  <h1 v-if="isShowing" v-html="title"></h1>
  <p v-else>test</p>
</template>
<script>
export default {
  data() {
    return {
      title: '<div>hello osas</div>',
      isShowing: true,
    }
  },
}
</script>
