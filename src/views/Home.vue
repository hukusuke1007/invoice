<template>
  <div class="home">
    <InvoiceCode msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import InvoiceCode from '@/components/InvoiceCode.vue'; // @ is an alias to /src

@Component({
  components: {
    InvoiceCode,
  },
})
export default class Home extends Vue {}
</script>
