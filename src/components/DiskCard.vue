<template>
    <div class="disk-card">

        <!-- Poster  -->
        <div class="poster">
            <img :src="diskObject.poster" :alt="diskObject.title">
        </div>

        <!-- Disk Title  -->
        <div class="title">{{ diskObject.title }}</div>

        <!-- Author  -->
        <div class="author">{{ diskObject.author }}</div>

        <!-- Date  -->
        <div class="year">{{ diskObject.year }}</div>
    </div>
</template>

<script>
export default {
    name: 'DiskCard',
    props: {
        diskObject : Object
    }
}
</script>

<style lang="scss" scoped>

.disk-card {
    padding: 20px 20px 50px 20px;
    background-color: #2e3a46;
    width: calc((100% / 5) - 40px);
    margin-bottom: 30px;
    
    // Poster 
    .poster {
        width: 100%;
        margin: 0 auto 15px;
    }

    // Title 
    .title {
        text-align: center;
        text-transform: uppercase;
        color: white;
        font-size: 27px;
        margin-bottom: 20px;
    }

    .author,
    .year {
        color: #736f6d;
        text-align: center;
        font-size: 18px;
    }
}
</style>