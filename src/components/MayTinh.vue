

<script>
import NutBanPhim from "@/components/NutBanPhim.vue";
export default {
  name: 'MayTinh',
  components: {
    NutBanPhim ,
  },
  props: {
    ten: String
  },

data() {
    return {
      displayValue: ''
    }
  },
  methods: {
    handleButtonClick(value) {
      switch (value) {
        case '=':
          this.tinhtoan();
          break;
        case 'DEL':
          this.deleteData();
          break;
        case 'ALC':
          this.resetDisplay();
          break;
        default:
          this.appendToDisplay(value);
      }
    },
    tinhtoan(){
      try {
        this.displayValue=eval(this.displayValue);
      } catch (e) {
        this.displayValue="error"
      }

    },
    appendToDisplay(value) {
      this.displayValue += value;
    },
    resetDisplay() {
      this.displayValue = ''; // Trả về giá trị của ô input về rỗng
    },
    // Phương thức để xóa dữ liệu
    deleteData() {
      this.displayValue = this.displayValue.slice(0,-1); // Xóa nội dung displayValue
    }
  }
}
</script>

<template>
  <div>
    <h1>{{ ten }}</h1>
    <div  class="calculator">
      <h3 id="one"> CASINO</h3>
      <h3 id="two"> FX580</h3>
      <input type="" class="display" v-model="displayValue">
      <div class="button-operation">


        <NutBanPhim Nut= "7" @nutClicked="handleButtonClick" ></NutBanPhim>
        <NutBanPhim Nut= "8" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "9" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "DEL" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "ALC" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "4" @nutClicked="handleButtonClick">  </NutBanPhim>
        <NutBanPhim Nut= "5" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "6" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "*" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "/" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "1" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "2" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "3" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "+" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "-" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "0" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "(" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= ")" @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "." @nutClicked="handleButtonClick"></NutBanPhim>
        <NutBanPhim Nut= "=" @nutClicked="handleButtonClick"></NutBanPhim>
      </div>


<!--        <button class="btn" @click="appendToDisplay(7)">7</button>-->
<!--        <button class="btn" @click="appendToDisplay(8)">8</button>-->
<!--        <button class="btn" @click="appendToDisplay(9)">9</button>-->
<!--        <button class="btn operation" @click="deleteData()">DEL</button>-->
<!--        <button class="btn operation" @click="resetDisplay()">ALC</button>-->

<!--        <button class="btn" @click="appendToDisplay(4)">4</button>-->
<!--        <button class="btn" @click="appendToDisplay(5)">5</button>-->
<!--        <button class="btn" @click="appendToDisplay(6)">6</button>-->
<!--        <button class="btn operation">*</button>-->
<!--        <button class="btn operation">/</button>-->

<!--        <button class="btn" @click="appendToDisplay(1)">1</button>-->
<!--        <button class="btn" @click="appendToDisplay(2)">2</button>-->

<!--        <button class="btn operation" >+</button>-->
<!--        <button class="btn operation" >-</button>-->

<!--        <button class="btn" @click="appendToDisplay(0)">0</button>-->
<!--        <button class="btn operation" >.</button>-->
<!--        <button class="btn operation" >(</button>-->
<!--        <button class="btn operation" >)</button>-->
<!--        <button class="btn operation">=</button>-->
      </div>

    </div>

</template>


<style scoped>
.calculator{
  width: 400px;
  margin: auto;
  padding: 50px;
  border: 16px solid #ccc;
  border-radius: 46px;
  background-color: royalblue;
  .display{
    width: auto;
    border-radius: 20px;
    font-size: 2em;
    text-align: right;
    padding-top: 10px;
  }
  .button-operation{
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 10px;
  }

  #one{
   float: left;
  }
  #two{
    float: right;
  }

}

</style>