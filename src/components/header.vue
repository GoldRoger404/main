<template>
    <div class="header">
        <div class="logo">
            <img src="../assets/logo33.png" alt="logo">
        </div>
        <div>
            Форма
        </div>
        <div class="title-block">
            Превью
        </div>
    </div>
</template>
<script>

export default {
    name: 'Header'
}
</script>
<style lang="css" scoped>
.header{
    width:100%;
    background: #FFFFFF;
    height: 76px;
    display: flex;
    justify-content: center;
    align-items: center;
    color: rgba(4, 3, 73, 0.48);
    box-shadow: 0px 1px 0px rgba(17, 17, 17, 0.1);
}
img{
    width: 100%;
}
.logo{
    width:70px;
    position: absolute;
    left:10%;
    top:0;
    overflow: hidden;
}
.title-block{
    margin-left:24px;
}

</style>