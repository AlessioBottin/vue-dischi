<template>
    <header>
        <div class="logo-container">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/71/Spotify.png/600px-Spotify.png" alt="logo spotify">
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style lang="scss" scoped>
    header {
        background-color: #2e3a46;
        padding: 20px 30px;
        
        .logo-container {
            width: 60px;
        }
    }
</style>