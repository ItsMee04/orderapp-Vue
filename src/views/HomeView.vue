<template lang="">
  <NavBar :name=userName />
  <div class="page-wrapper">
    <div class="content">
      <div class="row">
        <div class="col-xl-3 col-sm-6 col-12 d-flex">
          <div class="dash-widget w-100">
            <div class="dash-widgetimg">
              <span
                ><img src="/src/assets/img/icons/dash1.svg" alt="img"
              /></span>
            </div>
            <div class="dash-widgetcontent">
              <h5>
                $<span class="counters" data-count="307144.00"
                  >$307,144.00</span
                >
              </h5>
              <h6>Total Purchase Due</h6>
            </div>
          </div>
        </div>
        <div class="col-xl-3 col-sm-6 col-12 d-flex">
          <div class="dash-widget dash1 w-100">
            <div class="dash-widgetimg">
              <span
                ><img src="/src/assets/img/icons/dash2.svg" alt="img"
              /></span>
            </div>
            <div class="dash-widgetcontent">
              <h5>
                $<span class="counters" data-count="4385.00">$4,385.00</span>
              </h5>
              <h6>Total Sales Due</h6>
            </div>
          </div>
        </div>
        <div class="col-xl-3 col-sm-6 col-12 d-flex">
          <div class="dash-widget dash2 w-100">
            <div class="dash-widgetimg">
              <span
                ><img src="/src/assets/img/icons/dash3.svg" alt="img"
              /></span>
            </div>
            <div class="dash-widgetcontent">
              <h5>
                $<span class="counters" data-count="385656.50"
                  >$385,656.50</span
                >
              </h5>
              <h6>Total Sale Amount</h6>
            </div>
          </div>
        </div>
        <div class="col-xl-3 col-sm-6 col-12 d-flex">
          <div class="dash-widget dash3 w-100">
            <div class="dash-widgetimg">
              <span
                ><img src="/src/assets/img/icons/dash4.svg" alt="img"
              /></span>
            </div>
            <div class="dash-widgetcontent">
              <h5>
                $<span class="counters" data-count="40000.00">$400.00</span>
              </h5>
              <h6>Total Expense Amount</h6>
            </div>
          </div>
        </div>
        <div class="col-xl-3 col-sm-6 col-12 d-flex">
          <div class="dash-count">
            <div class="dash-counts">
              <h4>100</h4>
              <h5>Customers</h5>
            </div>
            <div class="dash-imgs">
              <i data-feather="user"></i>
            </div>
          </div>
        </div>
        <div class="col-xl-3 col-sm-6 col-12 d-flex">
          <div class="dash-count das1">
            <div class="dash-counts">
              <h4>110</h4>
              <h5>Suppliers</h5>
            </div>
            <div class="dash-imgs">
              <i data-feather="user-check"></i>
            </div>
          </div>
        </div>
        <div class="col-xl-3 col-sm-6 col-12 d-flex">
          <div class="dash-count das2">
            <div class="dash-counts">
              <h4>150</h4>
              <h5>Purchase Invoice</h5>
            </div>
            <div class="dash-imgs">
              <img
                src="/src/assets/img/icons/file-text-icon-01.svg"
                class="img-fluid"
                alt="icon"
              />
            </div>
          </div>
        </div>
        <div class="col-xl-3 col-sm-6 col-12 d-flex">
          <div class="dash-count das3">
            <div class="dash-counts">
              <h4>170</h4>
              <h5>Sales Invoice</h5>
            </div>
            <div class="dash-imgs">
              <i data-feather="file"></i>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import router from "@/router";
import NavBar from "@/components/NavBar.vue";

export default {
  components: {
    NavBar
  },
  data() {
    return {
      userName: "",
    };
  },

  mounted() {
    this.userName = localStorage.getItem("name");
    if (!this.userName || this.userName == null) {
      router.push({ name: "login" });
    }
  },
};
</script>
<style lang=""></style>
