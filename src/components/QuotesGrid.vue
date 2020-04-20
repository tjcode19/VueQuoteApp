<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" :key="quote.index" @click.native="deleteQuote(index)">{{ quote }}</app-quote>
    </div>
</template>
<script>
    import Quote from '../components/Quotes.vue'
    export default {
        props:['quotes'],
        components:{
            appQuote:Quote
        },
        methods:{
            deleteQuote(index){
                this.$emit('appDeleteQuote', index);
            }
        }        
    }
</script>
<style scoped>

</style>