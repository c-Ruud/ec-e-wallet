<template>
  <div class="add-cards">
    <top></top>

    <card-item :card="card"> </card-item>

    <card-form class="add-card" v-on:newCardEx="showCardInfo"> </card-form>

    <a href="#" class="cta" v-on:click="$router.push({ path: '/' })"
      >Back to your e-wallet</a
    >
  </div>
</template>

<script>
import CardForm from "@/components/CardForm.vue";
import Top from "@/components/Top.vue";
import CardItem from "@/components/CardItem.vue";

export default {
  name: "addCard",
  components: {
    CardForm,
    Top,
    CardItem,
  },
  data() {
    return {
      card: {},
    };
  },
  methods: {
    showCardInfo(myCard) {
      this.card = {
        idCard: myCard.idCard,
        fullName: myCard.fullName,
        cardNumber: myCard.cardNumber,
        month: myCard.month,
        year: myCard.year,
        vendor: myCard.vendor,
      };
    },
  },
};
</script>

<style scoped></style>
