<template>
    <div class="container">
        <appHeader :count="quotesList.length"  ></appHeader>
        <appQuoteAdder @dataSent="increaseCounter"></appQuoteAdder>
        <div 
                class="textCard" 
                :key="input.value"
                @click="deleteTextbox(index)" 
                v-for="(input, index) in quotesList" >
            <p >  {{input}} </p>
        </div>
        <appBanner></appBanner>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import Quoteadder from './components/Quoteadder.vue'
    import Infobanner from './components/Infobanner.vue'
    import Quoute from './components/Quote.vue';

    export default {
        data: function () {
            return {
                quotesList: ["this is the first quote"],
              
            }
        },
        methods: {
            increaseCounter (text) {
                 if (this.quotesList.length >= 10 ) {
                     alert ("Delete a quote before adding more :)")
                 } else
                this.quotesList.push(text)
            },
           deleteTextbox (index) {
                this.quotesList.splice(index, 1)
           } 
        },
          
        components: {
            appHeader: Header, 
            appQuoteAdder: Quoteadder,
            appBanner: Infobanner,
            appQuoute: Quoute
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
    width: 250px;
    display: inline-block;
    margin: 30px; 
    font-family: 'Arizonia', sans-serif;
    font-style: italic;
    background: royalblue;
    color: white; 
    border-radius: 10px;
 }

 .textCard:hover {
    background: #4169e199;
  transition: .5s ease;
  border-radius: 10px;
  color: #fff;
  transform: scale(1.2);
  box-sizing: border-box;
}
</style>
