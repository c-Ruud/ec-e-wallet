<template>
  <div class="about">
    <top></top>
    <h3>This is an e-wallet</h3>
    <h5>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Tempora velit
      exercitationem sequi possimus, mollitia at aperiam quam placeat iure ea,
      ipsa impedit delectus hic praesentium. Repellat odio eum asperiores in.
    </h5>

    <h3>e-wallet is for your safety</h3>
    <h5>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Tempora velit
      exercitationem sequi possimus, mollitia at aperiam quam placeat iure ea,
      ipsa impedit delectus hic praesentium. Repellat odio eum asperiores in.
    </h5>

    <h3>Why e-wallet?</h3>
    <h5>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Tempora velit
      exercitationem sequi possimus, mollitia at aperiam quam placeat iure ea,
      ipsa impedit delectus hic praesentium. Repellat odio eum asperiores in.
    </h5>

    <h3>Contact us at e-wallet</h3>
    <h5>
      Please be free to contact us when ever you want at:
      <a href="#">info@ewallet.not</a>
      <br />Ho mollitia at aperiam quam placeat iure ea,<br />
      ipsa impedit delectus hic praesentium. Repellat odio eum asperiores in.
    </h5>

    <hr />
    <br />
    <a href="#" class="cta" v-on:click="$router.push({ path: '/' })"
      >Back to your e-wallet</a
    >
  </div>
</template>
<script>
import Top from "@/components/Top.vue";
export default {
  components: {
    Top,
  },
};
</script>
<style scoped>
.about {
  text-align: center;
}
</style>
