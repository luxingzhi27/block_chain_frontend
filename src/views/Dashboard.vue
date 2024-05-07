<script setup>
// import MiniStatisticsCard from "@/examples/Cards/MiniStatisticsCard.vue";
// import GradientLineChart from "@/examples/Charts/GradientLineChart.vue";
// import CategoriesList from "./components/CategoriesList.vue";
import ArgonInput from "@/components/ArgonInput.vue";
import ArgonButton from "@/components/ArgonButton.vue";
import { ref } from "vue";

const productForm = ref({
  date: "",
  location: "",
});

// const product=()=>{
//   console.log(productForm.value)
// }

</script>
<template>
  <div class="py-4 container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <!-- <div class="row">
          <div class="col-lg-3 col-md-6 col-12">
            <mini-statistics-card
              title="Today's Money"
              value="$53,000"
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
          <div class="col-lg-3 col-md-6 col-12">
            <mini-statistics-card
              title="Today's Users"
              value="2,300"
              description="<span
                class='text-sm font-weight-bolder text-success'
                >+3%</span> since last week"
              :icon="{
                component: 'ni ni-world',
                background: 'bg-gradient-danger',
                shape: 'rounded-circle',
              }"
            />
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <mini-statistics-card
              title="New Clients"
              value="+3,462"
              description="<span
                class='text-sm font-weight-bolder text-danger'
                >-2%</span> since last quarter"
              :icon="{
                component: 'ni ni-paper-diploma',
                background: 'bg-gradient-success',
                shape: 'rounded-circle',
              }"
            />
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <mini-statistics-card
              title="Sales"
              value="$103,430"
              description="<span
                class='text-sm font-weight-bolder text-success'
                >+5%</span> than last month"
              :icon="{
                component: 'ni ni-cart',
                background: 'bg-gradient-warning',
                shape: 'rounded-circle',
              }"
            />
          </div>
        </div> -->
        <!-- <div class="row">
          <div class="col-lg-7 mb-lg">
              
            
          </div>
          <div class="col-lg-5">
            <carousel />
          </div>
        </div> -->
        <div class="row mt-4">
          <div class="col-lg-6 mb-lg-0 mb-4">
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
          <div class="col-lg-6">
            <div class="card">
                <div class="pb-0 card-header text-start">
                  <h4 class="font-weight-bolder">查询茅台酒</h4>
                  <p class="mb-0">输入茅台酒的编号</p>
                </div>
                <div class="card-body">
                  <form role="form">
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
                        fullWidth
                        size="lg"
                        >查询</argon-button
                      >
                    </div>
                  </form>
                </div>
              </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
