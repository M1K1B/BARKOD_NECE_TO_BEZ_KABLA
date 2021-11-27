<template>
  <div class="col-12 mx-auto p-3 p-md-5 main-div">
      <form class="mx-auto col-12">
          <div class="row mx-auto">
                <div class="col-12 col-md-5 mx-auto mb-4">
                    <label for="exampleInputEmail1" class="form-label">Konverzija iz:</label>
                    <input type="email" class="form-control mb-3" id="exampleInputEmail1" aria-describedby="emailHelp">
                    <select name="valuta-za" id="valuta-za" class="form-select">
                        <option value="EUR">EUR</option>
                    </select>
                </div>
                <img src="../assets/arrow-right-circle.svg" class="arrow mx-auto" alt="">
                <div class="col-12 col-md-5 mx-auto mb-4">
                    <label for="exampleInputEmail1" class="form-label">Konverzija u:</label>
                    <input type="email" class="form-control mb-3" id="exampleInputEmail1" aria-describedby="emailHelp">
                    <select name="valuta-za" id="valuta-za" class="form-select">
                        <option value="EUR"><i class="fa fa-caret-down" aria-hidden="true"></i>EUR</option>
                    </select>
                </div>
                <button class="btn btn-primary mx-auto col-11 col-md-4">Konvertuj</button>
          </div>
      </form>
  </div>
</template>

<script>
export default {

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