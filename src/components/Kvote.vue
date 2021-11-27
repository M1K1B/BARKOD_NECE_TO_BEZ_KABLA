<template>
    <div class="col-12 p-3 p-md-5 main-div">
        <h5 class="mb-4">Trenutne kvota:</h5>
        <table class="table col-12">
            <thead>
                <tr>
                    <th scope="col">Valuta</th>
                    <th scope="col">Vrednost</th>
                    <th scope="col">Promena (1M)</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td><img src="../assets/EUR.png" alt=""> EUR</td>
                    <td>1 EUR = {{ (1/this.rsdeur).toFixed(4) }} RSD</td>
                    <td class="gain_pos">{{ this.eurch }}%</td>
                </tr>
                <tr>
                    <td><img src="../assets/USD.png" alt=""> USD</td>
                    <td>1 USD = {{ (1/this.rsdusd).toFixed(4) }} RSD</td>
                    <td class="gain_pos">{{ this.eurch }}%</td>
                </tr>
                <tr>
                    <td><img src="../assets/JPY.png" alt=""> JPY</td>
                    <td>1 JPY = {{ (1/this.rsdjpy).toFixed(4) }} RSD</td>
                    <td class="gain_neg">{{ this.eurch }}%</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            rsdeur: '',
            rsdusd: '',
            rsdjpy: '',
            _rsdeur: '',
            _rsdusd: '',
            _rsdjpy: '',
            eurch: '',
            usdch: '',
            jpych: ''
        }
    },
    methods: {
        changeeur(){
            axios.get('https://api.currencylayer.com/historical?source=RSD&currencies=EUR,USD,JPY&date=2021-11-26&access_key=96c7a03cce11e464756d645302fbb324')
                .then(response => {
                    this._rsdeur = parseDouble(response.data.quotes.RSDEUR)
                    this._rsdusd = parseDouble(response.data.quotes.RSDUSD)
                    this._rsdjpy = parseDouble(response.data.quotes.RSDJPY)
                }).catch(e => {this.errors.push(e)})

            this.eurch = ((parseDouble(this.rsdeur)/parseDouble(this._rsdeur))*100)-100
        },
        changeusd(){
            axios.get('https://api.currencylayer.com/historical?source=RSD&currencies=EUR,USD,JPY&date=2021-11-26&access_key=96c7a03cce11e464756d645302fbb324')
                .then(response => {
                    this._rsdeur = parseDouble(response.data.quotes.RSDEUR)
                    this._rsdusd = parseDouble(response.data.quotes.RSDUSD)
                    this._rsdjpy = parseDouble(response.data.quotes.RSDJPY)
                }).catch(e => {this.errors.push(e)})

            this.usdch = ((this.rsdusd/this._rsdeur)*100)-100
        },
        changejpy(){
            axios.get('https://api.currencylayer.com/historical?source=RSD&currencies=EUR,USD,JPY&date=2021-11-26&access_key=96c7a03cce11e464756d645302fbb324')
                .then(response => {
                    this._rsdeur = parseDouble(response.data.quotes.RSDEUR)
                    this._rsdusd = parseDouble(response.data.quotes.RSDUSD)
                    this._rsdjpy = parseDouble(response.data.quotes.RSDJPY)
                }).catch(e => {this.errors.push(e)})

            this.jpych = ((this.rsdjpy/this._rsdjpy)*100)-100
        }
    },
    mounted() {
        this.api="https://api.currencylayer.com/live?source=RSD&access_key=96c7a03cce11e464756d645302fbb324"
        axios.get(this.api)
        .then(response => {
            this.rsdeur = response.data.quotes.RSDEUR
            this.rsdusd = response.data.quotes.RSDUSD
            this.rsdjpy = response.data.quotes.RSDJPY

            console.log(this.rsdeur + " | " + this.rsdusd + " | " + this.rsdjpy)
        }).catch(e => {this.errors.push(e)})

        this.changeeur()
        this.changeusd()
        this.changejpy()
    }
}
</script>

<style scoped>
option img{
    width: 20px;
}
.main-div{
    border-radius: 8px;
    background-color: white;
    box-shadow: rgb(36 36 107 / 30%) 0px 6px 12px;
    
}
.arrow{
    width: 50px;
}

button{
    background-color: white;
    border-color: rgb(205, 205, 205);
    color: black;
    text-align: left;
    margin-bottom: 15px;
}

td img{
    width: 24px;
    margin-right: 10px;
}
.gain_pos{
    color: green;
}
.gain_neg{
    color: red;
}
</style>