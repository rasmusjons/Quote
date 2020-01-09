<template>
    <div>
        <p v-for="quote in quotes"> {{ quote }}</p>
    </div>   
</template>

<script>
export default {

    props: {
        count: ['quotes']
    },
  

   

}

</script>

<style scoped>

</style>