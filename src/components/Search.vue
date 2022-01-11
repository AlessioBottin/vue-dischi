<template>
    <div class="search">
        <div class="filter">
                <select @change="$emit('filter', genreFilter)" v-model="genreFilter" name="genre" id="">
                    <option value="all">All</option>
                    <option value="rock">Rock</option>
                    <option value="pop">Pop</option>
                    <option value="jazz">Jazz</option>
                    <option value="metal">Metal</option>
                </select>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Search',
    data: function() {
        return {
            genreFilter: 'all',
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../style/variables';

// Select 
.filter {
    margin-bottom: 30px;

    select {
        color: white;
        background-color: $secondary_color;
        border-color: white;
        padding: 10px 5px;
        font-size: 18px;
        border-radius: 10px;
    }
} 
</style>