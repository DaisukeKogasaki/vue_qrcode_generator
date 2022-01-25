<template>
  <v-app>
    <div id="qr-code">
      <qrcode-vue :value="value" :size="size" level="H" render-as="svg" />
    </div>
    <div><span>変換内容</span></div>
    <div><textarea type="textarea" id="qr-val" /></div>
    <div><button @click="generate()">変換</button></div>

  </v-app>
</template>

<script>
  import QrcodeVue from 'qrcode.vue'

  export default {
    data() {
      return {
        value: 'https://example.com',
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
    margin-bottom: 8px;
  }

  span {
    text-align: center;
  }

  textarea, button {
    width: 300px;
  }

  textarea {
    height: 100px;
    max-width: 300px;
    min-width: 300px;
  }
</style>
