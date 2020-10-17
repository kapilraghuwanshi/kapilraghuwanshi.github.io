<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <p>Edit <code>components/Home.vue</code> to test hot module replacement.</p>
</template>

<script>
export default {
  name: 'Home',
  props: {
    msg: String
  },
  data() {
    return {
      count: 0
    }
  }
}
</script>

