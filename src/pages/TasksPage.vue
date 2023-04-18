<template>
  <q-page class="q-pa-md row items-start q-gutter-md">
    <task
      v-for="(item, item_index) in data"
      :key="item_index"
      :data="item"
    ></task>
  </q-page>
</template>

<script>
import { defineComponent, defineAsyncComponent } from "vue";

// taskType: {
//   1: "外搬",
//   2: "回搬"
// }
// orderType: {
//   1: "系統待轉運自動派送",
//   11: "人工下游叫料",
//   12: "人工上游出貨",
//   13: "人工上游轉單"
// }

// carryingType: {
//   1: "裝車",
//   2: "卸車"
// }

const data = [
  {
    id: "02",
    from: "APX",
    to: "NX yard",
    createdDate: "2023-04-18 08:04:27",
    coilCount: 4,
    finishedCoilCount: 4,
    lastFinishedDate: "2023-04-18 08:04:27",
    type: "外搬",
    orderType: "系統待轉運自動派送",
    remark: "",
  },
  {
    id: "03",
    from: "NX yard",
    to: "N6X yard",
    createdDate: "2023-04-18 08:04:27",
    coilCount: 5,
    finishedCoilCount: 2,
    lastFinishedDate: "2023-04-18 08:04:27",
    type: "外搬",
    orderType: "系統待轉運自動派送",
    remark: "",
  },
  {
    id: "04",
    from: "NX yard",
    to: "TPX",
    createdDate: "2023-04-18 08:04:27",
    coilCount: 3,
    finishedCoilCount: 0,
    lastFinishedDate: "",
    type: "外搬",
    orderType: "系統待轉運自動派送",
    remark: "",
  },
];

export default defineComponent({
  components: {
    Task: defineAsyncComponent(() => import("components/TaskCard.vue")),
  },
  name: "TasksPage",
  setup() {
    return {
      data,
    };
  },
});
</script>
