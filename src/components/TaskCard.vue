<template>
  <q-card
    class="cursor-pointer"
    @click="this.$router.push({ path: `/tasks/${data.id}` })"
  >
    <q-card-section>
      <div class="text-h6">任務 - {{ data.id }}</div>
      <div class="text-subtitle2">{{ data.from }} -> {{ data.to }}</div>
      <div class="">鋼捲數量 - {{ data.coilCount }}</div>
      <div class="">任務開始 - {{ data.createdDate }}</div>
      <p>備註 - {{ data.remark }}</p>
    </q-card-section>
    <q-card-section
      class="bg-blue"
      :class="{ 'bg-green': data.coilCount === data.finishedCoilCount }"
      v-if="data.lastFinishedDate"
    >
      <div>已完成鋼捲數量 - {{ data.finishedCoilCount }}</div>
      <div class="">最近裝卸時間 - {{ data.lastFinishedDate }}</div>
    </q-card-section>
  </q-card>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "TaskCard",
  props: ["data"],
});
</script>
