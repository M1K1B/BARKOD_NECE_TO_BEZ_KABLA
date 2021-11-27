<template>
    <div class="col-12 col-md-7 p-3 p-md-5 main-div">
        <div class="col-12 row">
            <select name="valuta-za" id="valuta-za" class="form-select">
                <option value="EUR">EUR</option>
            </select>
            <button class="btn btn-primary">Prikazi</button>
        </div>
        <canvas id="myChart" class="col-12"></canvas>
    </div>
</template>

<script>
import { Bar } from 'vue-chartjs'

export default {

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
    width: 100px;
    margin-left: 10px;
}
select{
    width: 200px;
}
</style>