<template>
  <div class="modal" v-if="show">
    <button @click="$emit('close')">Close</button>
  </div>
</template>

<script>
export default {
  props: {
    show: {
      type: Boolean,
      required: true
    }
  }
};
</script>
