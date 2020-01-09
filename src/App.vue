<template>
    <div class="container">
        <appHeader :count="quoteCount"  ></appHeader>
        <appQuoteAdder @dataSent="increaseCounter"></appQuoteAdder>
        <div 
            class="textCard" 
            :key="input.value"
            @click="deleteTextbox(index)" 
            v-for="(input, index) in qInput" >
             <p >  {{input}} </p>
        </div>
        <appBanner></appBanner>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import Quoteadder from './components/Quoteadder.vue'
    import Infobanner from './components/Infobanner.vue'

    export default {
        data: function () {
            return {
                quoteCount: 1,
                qInput: [],
              
            }
        },
        methods: {
            increaseCounter (text) {
                 if (this.quoteCount >= 10 ) {
                     alert ("maxat")
                 } else
                this.i++
                this.quoteCount++
                this.qInput.push(text)
            },
           deleteTextbox (index) {
                this.qInput.splice(index, 1)
           } 
        },
          
        components: {
            appHeader: Header, 
            appQuoteAdder: Quoteadder,
            appBanner: Infobanner
        }
        
    }
</script>

<style>
     .textCard {
    border: 1px solid #ccc;
    box-shadow: 1px 1px 2px black;
    font-size: 30px;
    padding: 30px; 
    margin: 30px auto;
    text-align: center;
    width: auto;
    display: inline-block;
    margin: 30px; 
    font-family: 'Arizonia', sans-serif;
    font-style: italic;
    background: royalblue;
    color: white; 
    border-radius: 10px;


     }
</style>
