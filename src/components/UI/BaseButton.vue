<template>
  <button :type="type" :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
   props: ['type', 'mode']
}
</script>


<style scoped>
button {
  padding: 5px 10px;
  font-family: inherit;
  background-color: brown;
  border: 1px solid brown;
  color: white;
  cursor: pointer;
  margin-right: 10px;
}
button:hover,
.button:active {
  background-color: rgb(184, 54, 54);
  border-color: rgb(184, 54, 54);
}

.flat {
  background-color: transparent;
  color: #3a0061;
  border: none;
  font-weight: bold;
}

.flat:hover,
.flat.active {
  background-color: #e7dcee;
}
</style>
