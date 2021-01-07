<template>
  <div class="card-form">
    <label for="number">Card number</label>
    <input
      class="col-2"
      type="text"
      name="number"
      maxlength="16"
      placeholder="XXXX XXXX XXXX XXXX"
      v-model="myCard.cardNumber"
      @input="$emit('newCardEx', myCard)"
    />

    <label for="fullName" class="col-2">Cardholder name</label>
    <input
      class="col-2"
      type="text"
      placeholder="Firstname and Lastname"
      v-model="myCard.fullName"
      @input="$emit('newCardEx', myCard)"
    />
    <label for="month" class="col-1">Month</label>
    <label for="year" class="col-1">Year</label>
    <select
      name="month"
      class="col-1"
      v-model="myCard.month"
      @change="$emit('newCardEx', myCard)"
    >
      <option value="01">01</option>
      <option value="02">02</option>
      <option value="03">03</option>
      <option value="04">04</option>
      <option value="05">05</option>
      <option value="06">06</option>
      <option value="07">07</option>
      <option value="08">08</option>
      <option value="09">09</option>
      <option value="10">10</option>
      <option value="11">11</option>
      <option value="12">12</option>
    </select>
    <select
      name="year"
      class="col-1"
      v-model="myCard.year"
      @change="$emit('newCardEx', myCard)"
    >
      <option value="21">21</option>
      <option value="22">22</option>
      <option value="23">23</option>
      <option value="24">24</option>
      <option value="25">25</option>
    </select>

    <label for="vendor" class="col-2">Vendor</label>
    <select
      name="vendor"
      class="col-2"
      v-model="myCard.vendor"
      @change="$emit('newCardEx', myCard)"
    >
      <option value="bitcoin">Bitcoin Inc</option>
      <option value="blockchain">Blockchain Inc</option>
      <option value="evil">Evil Corp</option>
      <option value="ninja">Ninja Bank</option>
    </select>
    <a href="#" class="cta col-2" v-on:click="addCard">Add card</a>
  </div>
</template>

<script>
export default {
  name: "CardForm",

  data() {
    return {
      myCard: {
        idCard: "",
        fullName: "",
        cardNumber: "",
        month: "",
        year: "",
        vendor: "",
      },
    };
  },
  methods: {
    addCard() {
      if (this.myCard.fullName.trim().length == 0) {
        return;
      }
      this.$root.cardInfo.push({
        id: Date.now(),
        fullName: this.myCard.fullName,
        cardNumber: this.myCard.cardNumber,
        month: this.myCard.month,
        year: this.myCard.year,
        vendor: this.myCard.vendor,
      });
      this.myCard.fullName = "";
      this.myCard.idCard++;
      (this.myCard.cardNumber = ""),
        (this.myCard.month = ""),
        (this.myCard.year = ""),
        (this.myCard.vendor = "");
    },
  },
};
</script>

<style lang="scss">
.card-form {
  margin: 1rem 0 0;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0 1rem;
  text-align: center;
}
.card-form label {
  font-size: 0.7rem;
  text-transform: uppercase;
  text-align: start;
  margin-top: 0.07rem;
}
.card-form input,
select {
  border: 1px solid #000;
  border-radius: 0.25rem;
  padding: 0.5rem;
  height: 2.6rem;
  margin: 0 0 0.8rem;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  font-size: 1rem;
  width: 100%;
}

input {
  -webkit-writing-mode: horizontal-tb !important;
  text-rendering: auto;
  color: -internal-light-dark(black, white);
  letter-spacing: normal;
  word-spacing: normal;
  text-transform: none;
  text-indent: 0px;
  text-shadow: none;
  display: inline-block;
  text-align: start;
  appearance: textfield;
  background-color: -internal-light-dark(rgb(255, 255, 255), rgb(59, 59, 59));
  -webkit-rtl-ordering: logical;
  cursor: text;
  margin: 0em;
  font: 400 13.3333px Arial;
  padding: 1px 2px;
  border-width: 2px;
  border-style: inset;
  border-color: -internal-light-dark(rgb(118, 118, 118), rgb(133, 133, 133));
  border-image: initial;
}
input[type="text" i] {
  padding: 1px 2px;
}
.col-2 {
  grid-column: auto/span 2;
}
.col-1 {
  grid-column: auto/span 1;
}
label {
  cursor: default;
}
</style>
