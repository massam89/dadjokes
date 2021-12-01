<template>
    <div class="container">
        <AppHeader />
        <h1>About DadJokes</h1>
        <p>This is an app that displays corny dad jokes</p>
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
            title: 'About the app',
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