<template>
    <div class="card">
    </div>
</template>

<script>

export default {
    name: 'CardProject'
}
</script>

<style scoped>
.card{
    width: 300px;
    height: 170px;
    border-radius: 20px;
    background-image: url('https://placeimg.com/640/480');
    background-position: center;
    background-repeat: no-repeat;
    background-size: 100%;
    cursor: pointer;
    transition: 400px;

}
.card:hover{
    background-size: 110%;
    transition: 400px;
}
</style>