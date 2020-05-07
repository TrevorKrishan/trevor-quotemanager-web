<template>
    <div class="newquote-container">
        <form>
            <div>
                <label for="">Enter Quote:</label>
                <textarea cols="50" rows="5" v-model="quote"></textarea>
            </div>
            <div>
                <button @click.prevent="createNew">Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data: function(){
            return {
                quote:''
            };
        },
        methods:{
            createNew(){
                this.$emit("quoteAdded",this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style scoped>
   .newquote-container{
       margin: 50px auto;
   } 
   form{
       width: fit-content;
       margin: 10px auto;
   }

   label{
       display: block;
       margin-bottom: 5px;
   }

   form > div{
       margin: 5px;
   }

   button{
       float: right;
       border-radius: 10px;
       background-color: rgb(51, 148, 204);
       padding: 10px;
       border: none;
       color:#fff;
   }

</style>  