<template>
  <div class="col-12 mx-auto p-3 p-md-5 main-div">
      <form class="mx-auto col-12" @submit.prevent="racun">
          <div class="row mx-auto">
                <div class="col-12 col-md-5 mx-auto mb-4">
                    <label for="exampleInputEmail1" class="form-label">Konverzija iz:</label>
                    <input type="text" v-model="unos" class="form-control mb-3" id="exampleInputEmail1" aria-describedby="emailHelp">
                    <select name="valuta-za" v-model="pvaluta" id="valuta-za" class="form-select">
                        <option value="RSD">RSD</option>
                        <option value="EUR">EUR</option>
                        <option value="USD">USD</option>
                        <option value="JPY">JPY</option>
                    </select>
                </div>
                <img @click="zamena" src="../assets/arrow-right-circle.svg" class="arrow mx-auto" alt="">
                <div class="col-12 col-md-5 mx-auto mb-4">
                    <label for="exampleInputEmail1" class="form-label">Konverzija u:</label>
                    <input type="text" v-model="vrednost" disabled class="form-control mb-3" id="exampleInputEmail1" aria-describedby="emailHelp">
                    <select name="valuta-za" v-model="dvaluta" id="valuta-za" class="form-select">
                        <option value="RSD">RSD</option>
                        <option value="EUR">EUR</option>
                        <option value="USD">USD</option>
                        <option value="JPY">JPY</option>
                    </select>
                </div>
                <button class="btn btn-primary mx-auto col-11 col-md-4">Konvertuj</button>
          </div>
      </form>
  </div>
</template>

<script>
import axios from 'axios';

export default {
    data(){
        return{
            api: '',
            unos: '',
            vrednost: '',
            pvaluta: 'RSD',
            dvaluta: 'EUR',
            zvaluta: '',
        }
    },
    methods:{
        racun(){
            this.api="https://api.currencylayer.com/convert?from=" + this.pvaluta + "&to=" + this.dvaluta + "&amount=" + this.unos + "&access_key=96c7a03cce11e464756d645302fbb324"
            axios.get(this.api)
            .then(response => {
                this.vrednost = response.data.result
            }).catch(e => {this.errors.push(e)})
            
        },
        zamena(){
            this.zvaluta=this.pvaluta
            this.pvaluta=this.dvaluta
            this.dvaluta=this.zvaluta
            this.racun()
        }
    }

}
</script>


<style scoped>
option img{
    width: 20px;
}
.main-div{
    margin-top: -150px;
    margin-left: 0;
    margin-right: 0;
    border-radius: 8px;
    background-color: white;
    box-shadow: rgb(36 36 107 / 30%) 0px 6px 12px;
}
.arrow{
    width: 50px;
}

button{
    margin-top: 20px;
    height: 50px;
    background-color: white;
    border-color: rgb(205, 205, 205);
    color: black;
}
</style>