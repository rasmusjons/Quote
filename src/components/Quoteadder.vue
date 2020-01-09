<template>
    <div>
        <textarea v-model="input" > </textarea>
        <button @click="counterIncrease">Add a quote</button>
    </div>
</template>

<script>

export default {
   data: function () {
       return{
           input: ""
       }
   },
   methods: {
        counterIncrease () {
            if (this.input === "") {
                return
            } else
             this.$emit("dataSent", this.input)
             this.input = ""
        }
     },
}
</script>

<style scoped>

    button {
        margin: auto;
        display: block;
        margin-left: auto;
        margin-right: auto;
        margin-top: 40px;
        font-family: 'Varela Round', sans-serif;
        font-size: 18px;
        text-transform: uppercase; 
        padding: 10px 15px;
        border-radius: 10px;
        margin-bottom: 30px;
        width: 150px;

}

button:hover {
  background-color: royalblue;
  cursor: pointer;
  color: white;
  
}


    textarea {
        font-family: 'Arizonia', sans-serif;
        width: 600px;
        height: 150px;
        display: block;
        margin-left: auto;
        margin-right: auto;
        border-radius: 25px;
        padding: 15px;
        font-size: 30px;


    }


    
</style>