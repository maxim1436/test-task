<template>
  <v-app>
    <div>
      <text-tags :textElements="TEXT_ELEMENTS" />
    </div><br />

    <div>
      <text-tags :textElements="TEXT_ELEMENTS" :justifyFull="true" />
    </div><br />

    <div style="width: 50%;">
      <text-tags :textElements="TEXT_ELEMENTS" />
    </div><br />

    <div style="width: 50%;">
      <text-tags :textElements="TEXT_ELEMENTS" :justifyFull="true" />
    </div><br />
    
  </v-app>
</template>

<script setup lang="ts">
import TextTags from './components/text-tags/TextTags.vue';
import { TextElem } from './types/types';

const TEXT_ELEMENTS = [
  {
    text: 4.3,
    icon: "star-outline"
  },
  {
    text: "Фридландские ворота",
  },
  {
    text: '1,2 км от вас'
  },
] as TextElem[];

</script>

<style scoped lang="scss">

div {
  padding: 0px;
  margin: 0px;
}

</style>
