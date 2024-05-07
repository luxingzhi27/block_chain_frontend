<script setup>
import MiniStatisticsCard from "@/examples/Cards/MiniStatisticsCard.vue";
// import GradientLineChart from "@/examples/Charts/GradientLineChart.vue";
// import CategoriesList from "./components/CategoriesList.vue";
import ArgonInput from "@/components/ArgonInput.vue";
import ArgonButton from "@/components/ArgonButton.vue";
import { ref } from "vue";

const productForm = ref({
  date: "",
  location: "",
  saleDate: "",
  id: "",
});

const resultForm = ref({
  date: new Date().toDateString(),
  location: "河北",
  saleDate: new Date().toDateString(),
  id: "9",
})

const nodeId=ref(0)

const todaySaleMount=ref(0) //今日销售量
const todayProductMount=ref(0) //今日生产量




// const product=()=>{
//   console.log(productForm.value)
// }

</script>
<template>
  <div class="py-4 container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <div class="row">
          <div class="col-lg-4 col-md-6 col-12">
            <mini-statistics-card
              title="今日销售量"
              :value="todaySaleMount.toString()"
              description="<span
                class='text-sm font-weight-bolder text-success'
                >+55%</span> since yesterday"
              :icon="{
                component: 'ni ni-money-coins',
                background: 'bg-gradient-primary',
                shape: 'rounded-circle',
              }"
            />
          </div>
          <div class="col-lg-4 col-md-6 col-12">
            <mini-statistics-card
              title="今日生产量"
              :value="todayProductMount.toString()"
              description="<span
                class='text-sm font-weight-bolder text-success'
                >+3%</span> since yesterday"
              :icon="{
                component: 'ni ni-world',
                background: 'bg-gradient-danger',
                shape: 'rounded-circle',
              }"
            />
          </div>
          <div class="col-lg-4">
            <div class="card">
              <div class="card-body">
                <div class="row p-2">
                  <div class="my-1.5 col-6 d-flex align-items-center">
                    <h5 class="mb-0">购买茅台酒</h5>
                  </div>
                  <div class="my-1.5 col-6 text-end">
                    <argon-button color="dark" variant="gradient">
                      购买
                    </argon-button>
                  </div>
                </div>
              </div>
              
            </div>
          </div>
        </div>
        <div class="row mt-4">
          <div class="col-lg-12 mb-lg-0 mb-4">
              <div class="card">
                <div class="pb-0 card-header text-start">
                  <h4 class="font-weight-bolder">生产茅台酒</h4>
                  <p class="mb-0">输入生产茅台酒的相关信息</p>
                </div>
                <div class="card-body">
                    <div class="mb-3">
                      <argon-input
                        id="date"
                        type="date"
                        placeholder="选择日期"
                        name="date"
                        size="lg"
                        v-model="productForm.date"
                      />
                    </div>
                    <div class="mb-3">
                      <argon-input
                        id="location"
                        placeholder="产地"
                        name="location"
                        size="lg"
                        v-model="productForm.location"
                      />
                    </div>
                    <div class="mb-3">
                      <argon-input
                        id="nodeId"
                        placeholder="生产节点编号"
                        name="nodeId"
                        size="lg"
                        v-model="nodeId"
                      />
                    </div>
                    <div class="text-center">
                      <argon-button
                        class="mt-4"
                        variant="gradient"
                        size="lg"
                        @click="console.log(productForm)"
                        >生产</argon-button
                      >
                    </div>
                </div>
              </div>
          </div>
          
          
      </div>
      <div class="row mt-4">
        <div class="col-lg-6 mb-4">
          <div class="card">
              <div class="pb-0 card-header text-start">
                <h4 class="font-weight-bolder">查询茅台酒</h4>
                <p class="mb-0">输入茅台酒的编号</p>
              </div>
              <div class="card-body">
                <div class="mb-3">
                  <argon-input
                    id="id"
                    placeholder="输入编号"
                    name="id"
                    size="lg"
                  />
                </div>
                <div class="text-center">
                  <argon-button
                    class="mt-4"
                    variant="gradient"
                    color="success"
                    size="lg"
                    >查询</argon-button
                  >
                </div>
              </div>
            </div>
            
          </div>
          <div class="col-lg-6 mb-4">
            <div class="card">
              <div class="pb-0 card-header text-start">
                <h4 class="font-weight-bolder">查询结果</h4>
              </div>
              <div class="card-body">
                <div class="mb-3">
                  <h6>编号: {{ resultForm.id }}</h6>
                  <h6>生产日期: {{resultForm.date  }}</h6>
                  <h6>产地: {{ resultForm.location }}</h6>
                  <h6>销售日期: {{ resultForm.saleDate }}</h6>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
