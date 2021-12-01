<template>
  <div class="container">
      <AppHeader />
      <h2>Welcome to the best corny dad jokes</h2>
  </div>
</template>

<script>
import AppHeader from '../components/AppHeader'

export default {
    components: {
        AppHeader
    },
    head() {
        return {
            title: 'Welcome to DadJokes',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Best place for corny dad jokes'
                }
            ]
        }
    }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
  background: #d8d6d6;
}
a {
  color: #666;
  text-decoration: none;
}
ul {
  list-style: none;
}
.container {
  max-width: 800px;
  margin: 2rem auto;
  overflow: hidden;
  padding: 1rem 2rem;
  background: #fff;
}
</style>
