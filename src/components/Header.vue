<template>
<div>
    <h2>Quotes Added</h2>
    <div class="backgroundProgressbar">
        <div class="progressBar" :style="{width: count + '0%'}"> 
            <p> {{count}} / 10</p>
        </div>
    </div>
 </div>   
</template>

<script>
export default {
    props: {
        count: Number
    },

}

</script>

<style scoped>
    .backgroundProgressbar {
        background: #eee;
        height: 20px;
        border-radius: 25px;
        margin-bottom: 30px;

    }

    .progressBar {
          font-family: 'Varela Round', sans-serif;

        background:royalblue;
        color: white;
        width: 10%;
        transition: width 1s;
        padding-left: 20px;
        height: 20px;
        border-radius: 25px;
    }

    h2 {
          font-family: 'Varela Round', sans-serif;

    }
</style>