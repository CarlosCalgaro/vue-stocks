<template>
    <b-card
        :title= stockSymbol
        tag="article"
        style="max-width: 20rem;"
        class="stock-box mb-2"
        v-bind:sub-title= "companyName"
    >
        <b-card-text class="stock-text">
            Price: U$ {{price}}
            <br>
            CEO: {{ceo}}
            <br>
            <p class="text-muted">
                Updated on: {{ this.lastUpdated }}
            </p>
            <p class="text-muted">
                On: {{ exchange }}
            </p>
        </b-card-text>
    </b-card>
</template>




<script>
import StockApi from '../../api/stocks/StockApi'
import moment from 'moment'
export default {
    name: 'stock-card',
    components: {
        StockApi,
        moment
    },
    props: {
        stockSymbol: String
    },
    data: () => {
        return {
            companyName: "",
            ceo: "",
            price: 0,
            lastUpdated: "", 
            exchange: ""
        }
    },
    methods: {
        refreshStock: function(){
            let self = this
            StockApi.Stocks.getPrice(self.stockSymbol).then((response)=>{
                self.price = response;
                self.lastUpdated = moment();
            });
        },
        loadStock: function(){
            let self = this;  
            StockApi.Stocks.byName(this.stockSymbol).then((response) => {
                self.companyName = response.companyName;
                self.ceo = response.CEO;
                self.exchange = response.exchange;
            });
        }
    },
    created: function(){
        let self = this;
        self.loadStock();
        self.refreshStock();
        setInterval(
           self.refreshStock,
           10000
        );
    },

    mounted: function(){
    }
}

</script>



<style>
   
code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, "Courier New",
    monospace;
}

.stock-title {
  text-align: center;
}

.stock-text {
  font-size: 0.8em
}
.stock-box {
  text-align: left;
  padding: 20px;
  background-color: whitesmoke;
  color: black;
}

</style>