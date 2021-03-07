<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        crud-test
      </h1>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
        <button type="button" @click="postData">POST</button>
        <button type="button" @click="getData">GET</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    async postData() {
      const response = await this.$axios.post('http://54.92.121.157/cars/', { name: 'test' })
      console.log(response)
    },
    async getData() {
      const response = await this.$axios.get('http://54.92.121.157/cars/')
      console.log(response)
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
