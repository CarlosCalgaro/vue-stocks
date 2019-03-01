<template>

    <div>
        <b-form  @reset="onReset" inline>
            <b-row>
                <b-form-input
                    id="stockSymbolInput"
                    type="text"
                    v-model="stock.symbol"
                    required
                    placeholder="Enter the symbol of stock"
                    class="mb-2" />
                <b-button class="mb-2 mr-2" v-on:click="submit()" variant="outline-info">Submit</b-button>
                <b-button class="mb-2 mr-2" type="reset"  variant="outline-danger">Reset</b-button>
            </b-row>
          
        </b-form>
    </div>
</template>



<script>
import StockCard from './StockCard';
export default {
    
    name: 'stock-form',
    components: {
        StockCard
    },
    data: function(){
        return{
            stock: {
                symbol: ""
            },
        }
    },
    methods:{
        submit: function(){
            this.$emit("stock-added", this.stock.symbol);
        },
        onReset: function(){
            this.$emit("stock-reset");
        }
    }
}

</script>



<style>

#stockSymbolInput{
    margin-right: 10px
}
</style>
