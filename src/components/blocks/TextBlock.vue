<template>
  <Editor v-if="!props.readonly" v-model="props.block.details.value"
    class="py-1.5" />
  <div v-else v-html="getRenderedValue(props.block.details.value)"
    class="py-1.5"></div>
</template>

<script setup lang="ts">
import { PropType, computed } from 'vue'
import { Block } from '@/utils/types'
import Editor from '../elements/Editor.vue'
import { getRenderedValue } from '@/utils/utils';

const props = defineProps({
  block: {
    type: Object as PropType<Block>,
    required: true,
  },
  readonly: {
    type: Boolean,
    default: false,
  },
})
</script>
