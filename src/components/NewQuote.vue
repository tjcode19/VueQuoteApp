<template>
    <div class="row">
        <form>
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                <label for=""></label>
                <textarea class="form-control" v-model="quote" rows="3"></textarea>
            </div>
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="addNewQuote">Add Quote</button>
            </div>
        </form>
    </div>
</template>
<script>
    export default {
       data: function(){
           return{
               quote:''
           }
       },
       methods:{
           addNewQuote(){
               this.$emit('newQuoteAdded', this.quote);
               this.quote = '';

           }
       }  
          
    }
</script>
<style scoped>

</style>