<template>
    
    <div>
    <b-container>
        <b-row>
            <b-col>
                <stock-form v-on:stock-reset="reset" v-on:stock-added="addStocks" ></stock-form>
            </b-col>
        </b-row>
    </b-container>
        <b-container >
            <b-row>
                <stock-card  v-for="stock in stocks" :key="stock" :stockSymbol="stock"></stock-card>
            </b-row> 
        </b-container>

    </div>
</template>



<script>
import StockCard from './StockCard';
import StockForm from './StockForm';
export default {
    
    name: 'stock-card-manager',
    components: {
        StockCard,
        StockForm
    },
    data: () => {
        return {
            mounted: false,
            stocks: []
        }
    },
    methods: {
        addStocks(stock){
            this.stocks.push(stock)
        },
        reset(){
            this.stocks = []
        }
    },
    mounted(){  
        this.mounted = true
    }
}

</script>



<style>

</style>
