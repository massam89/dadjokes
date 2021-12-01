<template>
    <div class="container">
        <AppHeader />
        <SearchJokes v-on:search-text="searchText"/>
        <Joke  v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"/>
    </div>
</template>

<script>
import axios from 'axios'
import AppHeader from '../../components/AppHeader'
import Joke from '../../components/Joke'
import SearchJokes from '../../components/SearchJokes'

export default {
    data() {
        return {
            jokes: []
        }
    },
    async created() {
        const config = {
            headers: {
                'Accept': 'application/json'
            }
        }

        try {
           const res = await axios.get('https://icanhazdadjoke.com/search', config);
           this.jokes = res.data.results;
        } catch (error) {
            console.log(error)
        }  
    },
    methods: {
        async searchText(text) {
            const config = {
                    headers: {
                'Accept': 'application/json'
                }
            }

            try {
            const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
            this.jokes = res.data.results;
            } catch (error) {
                console.log(error)
            } 
         }
    },
    components: {
        AppHeader,
        Joke,
        SearchJokes
    },
    head() {
        return {
            title: 'Dad Jokes',
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

<style scoped>

</style>