<script setup>
// import AuthorsTable from "./components/AuthorsTable.vue";
// import ProjectsTable from "./components/ProjectsTable.vue";

import { ref } from "vue";

function block(){
  return {
    index: 0,
    timestamp: "8893939",
    id: "333",
    product_date: new Date().toDateString(),
    product_location: "河北",
    product_sale_date: new Date().toDateString(),
    prevhash: "89990",
    hash: "83993hh",
  }
}

const blocks = ref([block(),block()]);
</script>
<template>
  <div class="py-4 container-fluid">
    <div class="row">
      <div class="col-12">
        <!-- <authors-table /> -->
        <div class="card">
          <div class="card-header pb-0">
            <h5 class="h5 mb-0">区块链展示</h5>
          </div>
          <div class="card-body px-0 pt-0 pb-2">
            <div class="table-responsive p-0">
              <table class="table align-items-center mb-0">
                <thead>
                  <tr>
                    <th
                      class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      Index
                    </th>
                    <th
                      class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7 ps-2"
                    >
                      Timestamp
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      id
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      product_date
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      product_location
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      product_sale_date
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      prevhash
                    </th>
                    <th
                      class="text-center text-uppercase text-secondary text-xxs font-weight-bolder opacity-7"
                    >
                      hash
                    </th>
                    <th class="text-secondary opacity-7"></th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(block,index) in blocks" :key="index">
                    <td><span class="text-xs font-weight-bold mx-3">{{ block.index }}</span></td>
                    <td><span class="text-xs font-weight-bold">{{ block.timestamp }}</span></td>
                    <td><span class="text-xs font-weight-bold mx-3">{{ block.id }}</span></td>
                    <td><span class="text-xs font-weight-bold mx-5">{{ block.product_date }}</span></td>
                    <td><span class="text-xs font-weight-bold mx-5">{{ block.product_location }}</span></td>
                    <td><span class="text-xs font-weight-bold mx-5">{{ block.product_sale_date }}</span></td>
                    <td><span class="text-xs font-weight-bold mx-5">{{ block.prevhash }}</span></td>
                    <td><span class="text-xs font-weight-bold mx-5">{{ block.hash }}</span></td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
        
      </div>
    </div>
  </div>
</template>
