<script>
import { defineComponent, ref, toRef } from "vue";
import SignUp from "../components/SignUp.vue";

export default defineComponent({
  name: "IndexPage",
  setup() {
    const registered = ref(false);
    const name = ref("");
    const url = ref("");
    const users = ref([]);
    // expose to template and other options API hooks
    return {
      registered,
      name,
      url,
      users,
    };
  },
  mounted() {
    console.log(this.registered);
  },
  components: { SignUp },
});

// 9RJXi3rAun4YDHzAEDmmVqNaYwdN4JXALrFeDGEjUZFB

//quarter cruel sugar foster cross plunge warm come column double lab eight

//New Wallet
// 3DJdyCwdNKupfNxi6aY1vehpgZ7DeCrzDfXJDdCttT9z

//repeat engage leaf unaware barrel cycle rally truck crazy language rocket deal
</script>
<template>
  <div class="wrapper">
    <div class="homeWrapper" v-if="registered === true">
      <div class="main">Hello</div>
    </div>
    <div class="signupContainer" v-else>
      <SignUp
        registered="registered"
        :name="name"
        :url="url"
        v-on:update:name="name = $event"
        v-on:update:url="url = $event"
      />
    </div>
  </div>
</template>

<style>
.center {
  flex: 1;
}
</style>
