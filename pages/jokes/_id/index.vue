<template>
    <div class="container">
        <AppHeader />
        <nuxt-link to="/jokes">Back to Jokes</nuxt-link>
        <h2>{{ joke }}</h2>
        <hr>
        <small>Joke ID: {{$route.params.id}}</small>
    </div>
</template>

<script>
import axios from 'axios'
import AppHeader from '../../../components/AppHeader'
export default {
    data() {
        return {
            joke: {}
        }
    },
    components: {
        AppHeader
    },
    async created() {
          const config = {
            headers: {
                'Accept': 'application/json'
            }
        }

        try {
           const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);
           this.joke = res.data.joke;
        } catch (error) {
            console.log(error)
        } 
    },
        head() {
        return {
            title: this.joke,
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