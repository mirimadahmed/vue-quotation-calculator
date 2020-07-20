<template>
    <div class="p-3">
        <h2 class="text-left">How many rooms?</h2>
        <p class="text-left">Let us know the number of your rooms.</p>
        <div class="form-group input-group-lg" id="holder">
            <small id="label" for="input">Lable</small>
                <input type="text" id="input" class="form-control">
        </div>
        <button type="button" class="btn btn-green btn-lg">Submit</button>
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
        padding-left: 15px;
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
    .btn-green {
        color: #002e11;
        background-color: #75f1a6;
        border-color: #4ded91;
    }
        
</style>
