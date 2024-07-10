<template>
  <div class="container">
    <ul :class="{ 'justify-full': justifyFull, 'align-left': !justifyFull, }">
      <template v-for="(elem, index) in textElements">
        <span :key="index" class="item">
          <v-icon v-if="elem.icon" :alt="elem.icon">
            mdi-{{ elem.icon }}
          </v-icon>
          {{ elem.text }}
        </span>
        <v-icon v-if="index < textElements.length - 1">mdi-circle-small</v-icon>
      </template>
    </ul>
  </div>
</template>

<script lang="ts" setup>
import { TextElem } from '@/types/types';
import { PropType } from 'vue';

defineProps({
  textElements: {
    type: Array as PropType<TextElem[]>,
    required: true,
  },

  justifyFull: {
    type: Boolean,
    required: false,
    default: false,
  }
})
</script>

<style lang="scss">
.container {
  overflow: hidden;
  max-height: 30px;
}

.item {
  display: inline-block;
  white-space: nowrap;
}

.container::after {
  content: '';
  display: block;
  height: 100%;
  width: 100%;
}

.align-left {
  text-align: left;
}

.justify-full {
  display: flex;
  justify-content: space-between;
}
</style>