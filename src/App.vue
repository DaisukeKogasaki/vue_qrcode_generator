<template>
  <div id="qr-code">
    <qrcode-vue :value="value" :size="size" level="H" render-as="svg" />
  </div>
  <div>変換内容</div>
  <div><textarea type="textarea" id="qr-val" /></div>
  <div><button @click="generate()">変換</button></div>
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
</style>
