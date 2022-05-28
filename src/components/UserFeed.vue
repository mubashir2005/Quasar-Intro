<template>
  <div></div>
</template>

<script>
import { createToaster } from "@meforma/vue-toaster";
import { TOKEN_PROGRAM_ID } from "@project-serum/anchor/dist/cjs/utils/token";
import { useWallet } from "solana-wallets-vue";
import { Solana_Host } from "../../utils/const";
export default {
  name: "UserFeed",
};
const toaster = createToaster({
  /* options */
});

toaster.show(`Hey! I'm here`);
</script>

<style scoped></style>
