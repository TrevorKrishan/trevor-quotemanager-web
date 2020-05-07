<template>
    <div class="panel-body quote">
        <slot></slot>    
    </div>
</template>

<script>
</script>

<style scoped>
    .panel-body{
        font-family: cursive;
        font-size: 24px;
        color: #6e6e6e;
        border: 1px solid #ccc;
        margin: 10px;
        padding: 10px;
        display: inline-block;
    }

    .quote{
        cursor: pointer;
    }

    .quote:hover{
        background-color: #ffe2e2;
    }
</style>  