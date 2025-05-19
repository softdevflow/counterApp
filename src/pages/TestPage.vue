<script setup lang="ts">

</script>

<template>
<q-page>
  <div class="Test">
    <h1 class="no-margin no-padding">TEST PAGE</h1>

  </div>

  <div class="flex flex-center q-ma-md">
    <q-btn color="red" rounded @click="$router.push('/')" label="MAIN PAGE" size="xl" />
  </div>
</q-page>
</template>

<style scoped>
.Test {
  display: flex;
  justify-content: center;
  justify-items: center;
  height: 100%;
  color: white;
}
</style>
