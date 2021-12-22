<template>
    <div class="disk-list">
        <div class="container">
            <div class="disk-container">
                <DiskCard v-for="(disk, index) in disks" :key="index" :diskObject="disk" />
                
            </div>
        </div>
    </div>
</template>

<script>
import DiskCard from "./DiskCard";
import axios from 'axios';

export default {
    name: 'DiskList',
    components: {
        DiskCard,
    },
    data: function() {
        return {
            disks: [],
        };
    },
    created: function() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.disks = response.data.response;
        });
    },
    
}
</script>

<style lang="scss" scoped>
.disk-list {
    background-color: #1e2d3b;

    .container {
        padding: 50px 0;

        .disk-container {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }
    }
}
</style>