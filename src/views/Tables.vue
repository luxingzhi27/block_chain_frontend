<script setup>
// import AuthorsTable from "./components/AuthorsTable.vue";
// import ProjectsTable from "./components/ProjectsTable.vue";

import {onMounted, ref} from "vue";
import axios from "axios";

function block(index,timestamp,id,produce_date,location,sale_date,prevhash,hash){
  return {
    index: index,
    timestamp: timestamp,
    id: id,
    produce_date: produce_date,
    location: location,
    sale_date: sale_date,
    prevhash: prevhash,
    hash: hash,
  }
}
const blocks = ref([]);

const getBlocks=()=>{
  axios.get('http://localhost:9000/').then((res)=>{
    if (res.data && res.data.status===10000){
      blocks.value=res.data.data.map((item)=>{
        return block(item.index,item.timestamp,item.maotai_data.id,item.maotai_data.produce_date,
            item.maotai_data.location,item.maotai_data.sale_date,item.prev_hash,item.hash)
      })
    }else {
      console.log(res.data.message)
    }
  })
}


onMounted(()=>{
  getBlocks()
})

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
                      produce_date
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
                    <td><span class="text-xs font-weight-bold mx-5">{{ block.produce_date }}</span></td>
                    <td><span class="text-xs font-weight-bold mx-5">{{ block.location }}</span></td>
                    <td><span class="text-xs font-weight-bold mx-5">{{ block.sale_date }}</span></td>
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
