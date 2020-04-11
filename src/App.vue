<template>
    <div id="app">
        <Header/>
        <div id="itens">
            <Box/>
        </div>
    </div>
</template>

<script>
import Header from './components/Header'
import Box from './components/Box'

export default {
    name: 'App',
    components: {
        Header,
        Box
    },
}
</script>

<style>
#app {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    text-shadow: 0.10rem 0.10rem rgba(128, 128, 128, 0.158);
}

input {
    box-shadow: 0.15rem 0.15rem rgba(128, 128, 128, 0.158)
}

button {
    box-shadow: 0.15rem 0.15rem rgba(128, 128, 128, 0.158)
}

#itens {
    margin: 2rem;
}
</style>

