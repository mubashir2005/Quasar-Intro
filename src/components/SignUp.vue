<template>
  <div class="wrapper">
    <wallet-multi-button dark></wallet-multi-button>
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
        <div class="inputTitle">
          User Name
          <span class="intructions">(Maximum Characters Allowed : 100 )</span>
        </div>
        <div class="inputContainer">
          <input
            class="inputField"
            required
            @change="nameChanged($event.target.value)"
          />
        </div>
      </div>
      <div class="fieldContainer">
        <div class="inputTitle">Profile Photo URL</div>
        <div class="inputContainer">
          <input
            class="inputField"
            required
            @change="urlChanged($event.target.value)"
          />
          <div class="randomUrl">Random</div>
        </div>
      </div>
      <div class="submitButton">Sign Up</div>
    </form>
  </div>
</template>

<script>
import "solana-wallets-vue/styles.css";

import { WalletAdapterNetwork } from "@solana/wallet-adapter-base";

import {
  PhantomWalletAdapter,
  SlopeWalletAdapter,
  SolflareWalletAdapter,
} from "@solana/wallet-adapter-wallets";

import { initWallet } from "solana-wallets-vue";
initWallet({
  wallets: [
    new PhantomWalletAdapter(),
    new SlopeWalletAdapter(),
    new SolflareWalletAdapter({ network: WalletAdapterNetwork.Devnet }),
  ],
  autoConnect: true,
});
import { WalletMultiButton } from "solana-wallets-vue";
export default {
  name: "SignUp",
  props: ["registered", "name", "url"],
  methods: {
    nameChanged(e) {
      this.$emit("update:name", {
        name: e,
      });
    },
    urlChanged(e) {
      this.$emit("update:url", {
        url: e,
      });
    },
  },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  width: min-content;
  height: 100%;
  border-radius: 1rem;
  background-color: #ffffff;
}
.title {
  font-size: 1.125rem;
  line-height: 1.75rem;
  font-weight: 600;
}
form {
  display: flex;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.fieldContainer {
  margin-top: 1rem;
  margin-bottom: 1rem;
}
.inputTitle {
  margin-bottom: 0.5rem;
  margin-left: 0.75rem;
  font-weight: 600;
}
.inputContainer {
  display: flex;
  display: flex;
  align-items: center;
  border-radius: 9999px;
}
.inputField {
  padding-left: 0.5rem;
  padding-right: 0.5rem;
  margin: 0.5rem;
  background-color: transparent;
  color: #14213d;
  flex: 1 1 0%;
  outline: 0;
}
.randomUrl {
  background-color: #14213d;
  padding-top: 0.25rem;
  padding-bottom: 0.25rem;
  padding-left: 0.5rem;
  padding-right: 0.5rem;
  margin-left: 0.25rem;
  margin-right: 0.25rem;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  color: #e5e5e5;
  height: 100%;
  border-radius: 9999px;
  cursor: pointer;
}
.submitButton {
  padding-top: 0.5rem;
  padding-bottom: 0.5rem;
  padding-left: 1rem;
  padding-right: 1rem;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  background-color: #14213d;
  color: #e5e5e5;
  font-weight: 600;
  border-radius: 9999px;
  cursor: pointer;
}
.instructions {
  font-style: italic !important;
}
</style>
