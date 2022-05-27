<template>
  <div class="wrapper">
    <div class="logoContainer">
      <img
        src="https://cdn4.iconfinder.com/data/icons/logos-brands-5/24/vue-dot-js-512.png"
        height="40"
        width="40"
        alt="Logo"
      />
    </div>
    <div class="title">Please sign in to use VTalk</div>
    <form>
      <div class="fieldContainer">
        <div class="inputTitle">Name</div>
        <div class="inputContainer">
          <input
            class="inputField"
            required
            @change="userName = $event.target.value"
          />
        </div>
      </div>
      <div class="fieldContainer">
        <div class="inputTitle">Profile Image URL</div>
        <div class="inputContainer">
          <input class="inputField" required />
        </div>
      </div>
    </form>
  </div>
</template>

<script>
import { ref, toRef } from "vue";

export default {
  name: "SignUp",
  props: ["registered", "name", "url"],
  setup(props) {
    const userName = toRef(props.name);
    return {
      userName,
    };
  },
};
</script>

<style scoped></style>
