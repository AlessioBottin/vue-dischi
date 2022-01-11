<template>
    <div class="disk-list">
        <div class="container">

            <Search @filter="setFilter"/>

            <div v-if="!isApiLoading" class="disk-container">
                <DiskCard v-for="(disk, index) in filterDisk" :key="index" :diskObject="disk" />               
            </div>

            <Loader v-else />
        </div>
    </div>
</template>

<script>
import DiskCard from "./DiskCard";
import Search from "./Search";
import Loader from "./Loader";
import axios from 'axios';

export default {
    name: 'DiskList',
    components: {
        DiskCard,
        Loader,
        Search,
    },
    data: function() {
        return {
            disks: [],
            isApiLoading: true,
            genreFilter: 'all',
        };
    },
    methods: {
        setFilter: function(genreText) {
            this.genreFilter = genreText
        }
    },
    computed: {
        filterDisk: function(genreText) {
            if (this.genreFilter === 'all') {
                return this.disks
            }

            const FilteredDisks = this.disks.filter((singleDisk) => {
                console.log(singleDisk.genre.toLowerCase());
                console.log(this.genreFilter);

                return singleDisk.genre.toLowerCase() === this.genreFilter;
            });
            
            return FilteredDisks;

        },
    },
    created: function() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.disks = response.data.response;
            this.isApiLoading = false;
        });
    },
    
}
</script>

<style lang="scss" scoped>
@import '../style/variables';

.disk-list {

    .container {
        padding: 50px 0;

        // Disk 
        .disk-container {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }
    }
}
</style>