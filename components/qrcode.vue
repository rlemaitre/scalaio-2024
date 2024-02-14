<script setup lang="ts">
import QRCodeVue3 from 'qrcode-vue3';
import {computed} from 'vue';

type Props = {
  url?: string;
  size?: number;
};
const {url, size} = withDefaults(defineProps<Props>(), {});

</script>
<template>
  <div>
    <QRCodeVue3
      :width="size"
      :height="size"
      :key="url"
      :value="url"
      :qrOptions="{ typeNumber: 0, mode: 'Byte', errorCorrectionLevel: 'H' }"
      :imageOptions="{ hideBackgroundDots: true, imageSize: 0.4, margin: 0 }"
      :dotsOptions="{
            type: 'dots',
            color: '#d32129',
            gradient: {
              type: 'linear',
              rotation: 0,
              colorStops: [
                { offset: 0, color: '#d32129' },
                { offset: 1, color: '#d32129' },
              ],
            },
          }"
      :backgroundOptions="{ color: '#transparent' }"
      :cornersSquareOptions="{ type: 'dot', color: '#d32129' }"
      :cornersDotOptions="{ type: undefined, color: '#d32129' }"
      fileExt="png"
      :download="true"
      myclass="my-qur"
      imgclass="img-qr"
      downloadButton="my-button"
      :downloadOptions="{ name: 'vqr', extension: 'png' }"
    />
  </div>
</template>
