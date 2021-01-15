<template>
  <div class="home">
    <top></top>
    <card-item @delete="deletea" :card="card" v-if="card" > </card-item>
    <card-stack  @showCard="click"></card-stack>
    <a href="#" class="cta" v-on:click="$router.push({ path: '/addcard' })"
      >Add a new card</a
    >
  </div>
</template>

<script>
import CardStack from "@/components/CardStack.vue";
import Top from "@/components/Top.vue";
import CardItem from "../components/CardItem.vue";

export default {
  name: "Home",
  components: {
    CardStack,
    Top,
    CardItem,
  },
  methods: {
    click(myCard) {
      this.card = {
        idCard: myCard.idCard,
        fullName: myCard.fullName,
        cardNumber: myCard.cardNumber,
        month: myCard.month,
        year: myCard.year,
        vendor: myCard.vendor,
      };
      return this.$root.cardInfo.idCard;
    },
    deletea(myCard) {
      /*this.$root.cardInfo = this.$root.cardInfo.filter(tabort => tabort.idCard != myCard.idCard);*/
      this.$root.cardInfo.splice(myCard, 1);
    }
  },
  data() {
    return {
      card: null,
    };
  },
};
</script>
<style lang="scss">
a.cta {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  height: 4rem;
  font-size: 1.2rem;
  text-transform: uppercase;
  font-weight: 700;
  text-decoration: none;
  color: #000;
  border: 0.125rem solid #000;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  border-radius: 0.5rem;
  margin: 0.4rem 0;
}
</style>
