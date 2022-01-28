<template>
  <v-app>
    <v-main>
      <v-container>
      <v-row>
        <v-col>
          <qrcode-vue :value="value" :size="size" level="H" render-as="svg" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-textarea id="qr-val" placeholder="生成内容" />
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-btn @click="generate()" block color="blue" text-color="white" >変換</v-btn>
        </v-col>
      </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
  import QrcodeVue from 'qrcode.vue'

  export default {
    data() {
      return {
        value: 'https://daisukekogasaki.github.io/vue_qrcode_generator/',
        size: 300,
      }
    },
    components: {
      QrcodeVue,
    },
    methods: {
      generate: function() {
        let qrElm = document.getElementById("qr-val");
        this.value = qrElm.value
      }
    },
  }

</script>

<style scoped>
  span, svg, textarea, button {
    display: block;
    margin-right: auto;
    margin-left: auto;
  }

  span {
    text-align: center;
  }

  textarea, button {
    width: 300px;
  }

</style>
