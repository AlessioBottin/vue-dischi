<template>
    <div class="loader">
        <span class="icon"><i class="fas fa-spinner"></i></span>
    </div>
</template>

<script>
export default {
    name: 'Loader',
}
</script>

<style lang="scss" scoped>
.loader {
    text-align: center;
    margin-top: 200px;
    animation: spin 2s infinite linear;

    .icon {
        color: white;
        font-size: 80px;
        
    }
}

@keyframes spin {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(359deg);
    }
}
</style>