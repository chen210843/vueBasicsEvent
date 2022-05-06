<template>
    <li>
        <img src="https://cdn-icons-png.flaticon.com/128/4521/4521022.png">
        <hr>
        <slot name="card-header"></slot>
        <slot name="card-content"></slot>
        <slot name="card-button"></slot>
    </li>

</template>
<script>
export default {
    name:"CardData"

}
</script>

<style scoped>
img{
    width: 100px;
    height: 100px;
}
</style>