<template>
  <div class="card blank" v-on:click="$emit('click')" :class="card.vendor">
    <header>
      <img src="../assets/chip-dark.svg" alt="chip" />
      <img
        v-if="card.vendor"
        :src="require('../assets/vendor-' + card.vendor + '.svg')"
        alt="vendor"
      />
    </header>
    <section class="number">
      {{ card.cardNumber }}
    </section>
    <section class="info">
      <aside class="holder">
        <span>Cardholder name</span>
        <p>{{ card.fullName }}</p>
      </aside>
      <aside>
        <span>mm/yy</span>
        <p>{{ card.month }}/{{ card.year }}</p>
      </aside>
    </section>
  </div>
</template>
<script>
export default {
  name: "card-item",
  props: {
    card: Object,
  },
};
</script>
<style lang="scss">
.blank {
  background: linear-gradient(
      237.75deg,
      hsla(0, 0%, 100%, 0.24),
      hsla(0, 0%, 100%, 0)
    ),
    #d0d0d0;
}

.card {
  max-width: 24rem;
  height: 14rem;
  border-radius: 0.6rem;
  background: #eee;
  padding: 1rem;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  -webkit-box-shadow: 0 0 0.5rem rgba(0, 0, 0, 0.4);
  box-shadow: 0 0 0.5rem rgba(0, 0, 0, 0.4);
  display: grid;
  gap: 0.5rem 0;
  grid-template-columns: 1fr 1fr;
  grid-auto-rows: 2.8rem;
  text-shadow: -1px -1px 2px hsla(0, 0%, 100%, 0.4);
}

.card header {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  grid-column: auto/span 2;
  grid-row: auto/span 2;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: space-between;
  -webkit-box-align: start;
  -ms-flex-align: start;
  align-items: flex-start;
}
.card section.info,
.card section.number {
  grid-column: auto/span 2;
  grid-row: auto/span 1;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
}
.card section.number {
  font-size: 1.6rem;
  letter-spacing: 0.05rem;
  padding: 0.5rem 0 0;
  text-transform: uppercase;
}
.card section.info aside.holder {
  -webkit-box-flex: 1;
  -ms-flexbox: 1;
  flex: 1;
}
aside {
  display: block;
}
.card section aside span {
  display: block;
  text-transform: uppercase;
  font-size: 0.7rem;
  margin: 0 0 0.25rem;
}
p {
  display: block;
  text-transform: uppercase;

  margin: 0 0 0.25rem;
}
.bitcoin {
  background: linear-gradient(
      0.689turn,
      hsla(0, 0%, 100%, 0.15),
      hsla(0, 0%, 100%, 0) 99.07%
    ),
    #ffae34;
  color: #222;
}
.ninja {
  background: linear-gradient(
      248.3deg,
      hsla(0, 0%, 100%, 0.15),
      hsla(0, 0%, 100%, 0)
    ),
    #222;
  background-image: linear-gradient(
      248.3deg,
      rgba(255, 255, 255, 0.15),
      rgba(255, 255, 255, 0)
    ),
    initial;
  background-color: rgb(34, 34, 34);
  color: #fff;
}
.blockchain {
  background: linear-gradient(248.52deg, rgba(0, 0, 0, 0.15) 1.49%, transparent),
    #8b58f9;
  color: #fff;
}
.evil {
  background: linear-gradient(248.3deg, rgba(0, 0, 0, 0.16), transparent),
    #f33355;
  color: #fff;
}
</style>
