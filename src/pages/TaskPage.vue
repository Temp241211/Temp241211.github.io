<template>
  <div class="q-pa-md example-column-mix-and-match">
    <!-- Stack the columns on mobile by making one full-width and the other half-width -->
    <div class="row" style="min-height: 150px">
      <div class="col col-sm col-xs-12 bg-blue">
        <p>任務 - {{ data.id }}</p>
        <p>地點 - {{ data.from }} -> {{ data.to }}</p>
        <p>鋼捲數量 - {{ data.coilcount }}</p>
      </div>
      <div
        class="col col-sm-4 col-xs-12 column"
        v-if="false"
        style="min-height: 75px"
      >
        <div class="col-6 bg-yellow">報到</div>
        <div class="col-6 bg-green">裝車完成</div>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <q-list bordered separator>
          <q-item v-ripple v-for="(item, idx) in data.carryings" :key="idx">
            <q-item-section>
              <q-item-label overline
                >[搬運作業{{ idx + 1 }}] - {{ item.type }}({{
                  item.plateNumber
                }})</q-item-label
              >
              <q-item-label v-if="item.checkIn"
                >報到時間 - {{ item.checkIn.date }}
                <span v-if="item.checkIn.coils && item.checkIn.coils.length > 0"
                  >({{ item.checkIn.coils.join() }})</span
                ></q-item-label
              >

              <q-item-label v-if="item.finished"
                >完成時間 - {{ item.finished.date }}
                <span
                  v-if="item.finished.coils && item.finished.coils.length > 0"
                  >({{ item.finished.coils.join() }})</span
                ></q-item-label
              >
            </q-item-section>
          </q-item>
        </q-list>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";

const data = {
  id: "02",
  from: "APX",
  to: "NX yard",
  createdDate: "2023-04-18 08:04:27",
  finishedCoilCount: 4,
  lastFinishedDate: "2023-04-18 08:04:27",
  coilcount: 4,
  type: "外搬",
  orderType: "系統待轉運自動派送",
  remark: "",
  carryings: [
    {
      id: "id01",
      plateNumber: "plateNumber01",
      type: "裝車",
      createDate: "2023-04-18 08:04:27",
      checkIn: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: [],
      },
      intoStock: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: [],
      },
      finished: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: ["12341234", "12341235"],
      },
      remark: "",
    },
    {
      id: "id02",
      plateNumber: "plateNumber01",
      type: "卸車",
      createDate: "2023-04-18 08:04:27",
      finishedCoils: [],
      checkIn: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: ["12341234", "12341235"],
      },
      intoStock: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: ["12341234", "12341235"],
      },
      finished: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: [],
      },
      remark: "",
    },
    {
      id: "id03",
      plateNumber: "plateNumber01",
      type: "裝車",
      createDate: "2023-04-18 08:04:27",
      checkIn: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: [],
      },
      intoStock: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: [],
      },
      finished: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: ["12341236", "12341237"],
      },
      remark: "",
    },
    {
      id: "id04",
      plateNumber: "plateNumber01",
      type: "卸車",
      createDate: "2023-04-18 08:04:27",
      checkIn: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: ["12341236", "12341237"],
      },
      intoStock: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: ["12341236", "12341237"],
      },
      finished: {
        date: "2023-04-18 08:04:27",
        type: 1,
        coils: [],
      },
      remark: "",
    },
  ],
};

export default defineComponent({
  name: "TaskPage",
  setup() {
    return {
      data,
    };
  },
});
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 350px
</style>
