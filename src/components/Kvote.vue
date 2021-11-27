<template>
    <div class="col-12 col-md-4 p-3 p-md-5 main-div">
        <h5 class="mb-4">Trenutne kvota:</h5>
        <table class="table col-12">
            <tbody>
                <tr>
                    <td><img src="../assets/EUR.png" alt=""> 1 EUR = 117.54 RSD</td>
                    <td class="gain_pos">+0.003%</td>
                </tr>
                <tr>
                    <td><img src="../assets/USD.png" alt=""> 1 EUR = 117.54 RSD</td>
                    <td class="gain_pos">+0.003%</td>
                </tr>
                <tr>
                    <td><img src="../assets/JPY.png" alt=""> 1 EUR = 117.54 RSD</td>
                    <td class="gain_neg">-0.003%</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import axios from 'axios';

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