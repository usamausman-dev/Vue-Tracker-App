<template>
  <button
    @click="$emit('btn-click')"
    :style="{ background: color }"
    class="btn"
  >
    <i class="fa-solid" :class="[icon ? 'fa-xmark' : 'fa-plus']"></i>

    {{ text }}
  </button>
</template>
<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
    icon: Boolean,
  },
};
</script>
