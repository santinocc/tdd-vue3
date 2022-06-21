<template>
  <img
  src="https://flagcdn.com/16x12/mx.png"
  srcset="https://flagcdn.com/32x24/mx.png 2x,
    https://flagcdn.com/48x36/mx.png 3x"
  width="28"
  height="21"
  alt="Mexico"
  title="Spanish" @click="$i18n.locale = 'es'">
  <img
  src="https://flagcdn.com/16x12/us.png"
  srcset="https://flagcdn.com/32x24/us.png 2x,
    https://flagcdn.com/48x36/us.png 3x"
  width="28"
  height="21"
  alt="United States"
  title="English" @click="$i18n.locale = 'en'">
</template>
<style scoped>
img {
  cursor: pointer;
}
</style>