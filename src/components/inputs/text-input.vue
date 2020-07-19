<template>
    <div class="form-group input-group-lg" id="holder">
        <small id="label" for="input">Lable</small>
            <input type="text" id="input" class="form-control">
    </div>
</template>

<script>
export default {};

</script>

<style>

    #holder {
    height: 50px;
    }
    #label {
        margin-bottom: -50px;
        padding-left: 5px;
        padding-top: 5px;
        position: absolute;
        color: #ccc;
        left: 10px;
        color: #4ded90;
    }
    #input {
        font-size: 15px;
        width: 100%;
        padding: 23px 25px 15px;
        border: 1px solid rgba(126,115,115,.55);
        margin-top: 0;
        height: 120%;
        border-color: #4ded90;
    }

</style>
