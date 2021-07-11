<template>
  <div id="app">
          <div >
              <div id="exchangePanel">
                <div id="btcBox"></div>
                <div id="btcTopBox"></div>
                <div id="btcBottomBox"></div>
                
                <h1 id="exchange">Exchange</h1>
                <p id="shitTalk">Trade stocks in an instant</p>
                <p id="from">From</p>
                <p id="to">To</p>
                
                <div id="fromChoose" @click="openModal()">
                  <img id="btcSwap" src="./assets/tsla.png" width="34" height="34">
                  <p id="btcSymbol">TSLA</p>
                </div>

                <div v-if="myModal">
                    <transition name="modal">
                        <div class="modal-mask">

                            <div id="modalFrom">
                              <hr id="modalLine">
                              <h1 id="selectStock">Select a Stock</h1>
                              <img src="./assets/cross.png" id="closeFrom" @click="myModal=false" width="13" height="13">
                            </div>
                            
                        </div>
                    </transition>
                </div>

                <div id="toChoose">
                  <img id="usdtSwap1" src="./assets/usdt.png" width="35" height="35">
                  <p id="usdtFont1">USDT</p>
                </div>

                <img id="settings" src="./assets/settings.png" width="35" height="35">
                <img id="clock" src="./assets/clock.png" width="29" height="29">
                <img id="swapArrow" src="./assets/arrow.png" width="60" height="50">
                <hr id="exchangeLine">
                <input id="btcSwapFrom" size="10" v-on:input="convert(btcname)" type="text" placeholder="0.0">
                <input id="btcSwapTo" size="10" type="text" placeholder="0.0" readonly>
                <button id="swapButton">Swap</button>
              </div>
          </div>
  </div>
</template>

<script>

export default {
  data(){
    return{
      btcname: "btc",
      myModal: false,
      actionButton: "Insert",
      dynamicTitle: "add niggers"
      
    }
  },
  methods: {
    toNumberString(num) { 
      if (Number.isInteger(num)) { 
        return num + ".0"
      } else {
      return num.toString(); 
      }
    },
    convert(nameOfCurrency){
      if (nameOfCurrency == this.btcname){
        let a = document.getElementById("btcSwapFrom").value;
        var val = parseFloat(a);
        var ratio = 32000;
        var sol = this.toNumberString(val * ratio);
        document.getElementById("btcSwapTo").value = sol;
      }
    },
    openModal(){
      console.log("js")
      this.myModal = true;
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Poppins:100,100i,200,200i,300,300i,400,400i,500,500i,600,600i,700,700i,800,800i,900,900i&subset=devanagari,latin-ext');

#app{
  font-family: 'Poppins', sans-serif;
	font-size: 16px;
	line-height: 24px;
	font-weight: 400;
	color: #14101b;
}
input{
  font-family: 'Poppins', sans-serif;
	font-size: 16px;
	line-height: 24px;
	font-weight: 400;
	color: #14101b;
}
body{
  background-image: linear-gradient(to right, rgba(192, 125, 247, 0.267),rgba(96, 210, 255, 0.333));
  background-color: black;
}



#btcSwap{
  position: absolute;
  left: 1055px;
  top: 403px;
}
#btcSymbol{
  position: absolute;
  left: 1095px;
  top: 391px;
}
#niceArrowSwapBtc{
  position: absolute;
  left: 900px;
  top: 100px;
}
#usdtSwap1{
  position: absolute;
  left: 1050px;
  top: 565px;
}
#usdtFont1{
  position: absolute;
  left: 1094px;
  top: 554px;
}


#btcBox {
  position: absolute;
  left: 672px;
  width: 370px;
  height: 450px;
  top: 170px;
  border-radius: 30px;
  background-color: white;
  padding: 50px;
  margin: 20px;
}
#btcTopBox {
  position: absolute;
  left: 687px;
  width: 340px;
  height: 10px;
  top: 325px;
  border-radius: 30px;
  background-color: rgb(197, 209, 214);
  padding: 50px;
  margin: 20px;
}
#btcBottomBox {
  position: absolute;
  left: 687px;
  width: 340px;
  height: 10px;
  top: 485px;
  border-radius: 30px;
  background-color: rgb(197, 209, 214);
  padding: 50px;
  margin: 20px;
}

#swapArrow{
  -webkit-transform:rotate(90deg);
  -moz-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  -o-transform: rotate(90deg);
  transform: rotate(90deg);
  position: absolute;
  left: 900px;
  top: 455px;
 
}
#btcSwapFrom{
  position: absolute;
  left: 730px;
  top: 402px;
  background-color: rgb(197, 209, 214);
  border: none;
}
::placeholder{
  color: #7c8085;
  font-size: 20px;
}
input {
 outline:none;
 font-size: 24px;
}

#btcSwapTo{
  position: absolute;
  left: 730px;
  top: 565px;
  border: none;
  background-color: rgb(197, 209, 214);
}

#exchangeLine{
  position: absolute;
  top: 300px;
  left: 691px;
  background-color: rgb(197, 209, 214);
  width: 469px;
}

#swapButton{
  position: absolute;
  background-color: rgb(89, 203, 252); /* Green */
  border: none;
  color: #ffffff;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  border-radius: 30px;
  font-family: 'Poppins', sans-serif;
  font-size: 20px;
  left: 755px;
  width: 340px;
  height: 60px;
  top: 650px;
}
#swapButton:hover{
  opacity: 0.7;
}

#exchange{
  position: absolute;
  left: 720px;
  font-size: 20px;
  font-weight: 600;
  top: 200px;
}

#shitTalk{
  position: absolute;
  left: 720px;
  color: #7c8085;
  font-size: 15px;
  top: 230px;
}

#settings{
  position: absolute;
  left: 1040px;
  filter: invert(76%) sepia(38%) saturate(1399%) hue-rotate(168deg) brightness(95%) contrast(108%);
  top: 225px;
}
#clock{
  position: absolute;
  left: 1100px;
  filter: invert(76%) sepia(38%) saturate(1399%) hue-rotate(168deg) brightness(95%) contrast(108%);
  top: 228px;
}

#fromChoose:hover{
    opacity: 0.7;
}
#toChoose:hover{
    opacity: 0.7;
}

.modal-mask {
     position: absolute;
     z-index: 9998;
     top: 0;
     left: 0;
     width: 100%;
     height: 100%;
     background-color: rgba(0, 0, 0, .5);
     display: table;
     transition: opacity .3s ease;
}

.modal-wrapper {
     display: table-cell;
     vertical-align: middle;
}

#modalFrom{
  position: absolute;
  left: 707px;
  width: 300px;
  height: 660px;
  top: 90px;
  border-radius: 30px;
  background-color: white;
  padding: 50px;
  margin: 20px;
}

#closeFrom{
  position: absolute;
  left: 340px;
  top: 48px;
  filter: invert(76%) sepia(38%) saturate(1399%) hue-rotate(168deg) brightness(95%) contrast(108%);

}
#closeFrom:hover{
  opacity: 0.7;
}
#selectStock{
  position: absolute;
  left: 40px;
  top: 30px;
  font-size: 20px;
  font-weight: 600;
}
#modalLine{
  position: absolute;
  top: 86px;
  left: 0px;
  background-color: rgb(197, 209, 214);
  width: 398px;
}
#from{
  position: absolute;
  top: 345px;
  left: 730px;
}
#to{
  position: absolute;
  top: 505px;
  left: 730px;
}
</style>
