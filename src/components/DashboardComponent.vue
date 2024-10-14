<template>
  <!-- Navbar -->

  <!-- /.navbar -->

  <HeaderComponent/>
  <SidebarComponent/>

  <!-- Content Wrapper. Contains page content -->
  <div class="content-wrapper">
    <!-- Content Header (Page header) -->
    <div class="content-header">
      <div class="container-fluid">
        <div class="row mb-2">
          <div class="col-sm-6">
            <h1 class="m-0"><b class="text-primary"><marquee behavior="" direction="">ຍິນດີຕອນຮັບເຂົ້າສູ່ລະບົບ</marquee></b></h1>
          </div><!-- /.col -->
          <div class="col-sm-6">
            <ol class="breadcrumb float-sm-right">
              <li class="breadcrumb-item"><router-link to="/dashboard" href="#">ໜ້າຫຼັກ</router-link></li>
              <li class="breadcrumb-item active">Dashboard</li>
            </ol>
          </div><!-- /.col -->
        </div><!-- /.row -->
      </div><!-- /.container-fluid -->
    </div>
    <!-- /.content-header -->

    <!-- Main content -->
    <section class="content">
      <div class="container-fluid">
        <!-- Small boxes (Stat box) -->
        <div class="row">
          <div class="col-lg-3 col-6">
            <!-- small box -->
            <div class="small-box bg-success">
              <div class="inner">
                <h4 class="text-bold">{{ sum_income }}</h4>

                <p>ລາຍຮັບທັງໝົດ</p>
              </div>
              <div class="icon">
                <i class="ion ion">₭</i>
              </div>
              <router-link to="/income_details" class="small-box-footer">ລາຍລະອຽດ <i class="fas fa-arrow-circle-right"></i></router-link>
            </div>
          </div>
          <!-- ./col -->
          <div class="col-lg-3 col-6">
            <!-- small box -->
            <div class="small-box bg-danger">
              <div class="inner">
                <h4 class="text-bold">{{ sum_expense }}</h4>

                <p>ລາຍຈ່າຍທັງໝົດ</p>
              </div>
              <div class="icon">
                <i class="ion">₭</i>
              </div>
              <router-link to="/expense_details" class="small-box-footer">ລາຍລະອຽດ<i class="fas fa-arrow-circle-right"></i></router-link>
            </div>
          </div>
          <!-- ./col -->
          <div class="col-lg-3 col-6">
            <!-- small box -->
            <div class="small-box bg-warning">
              <div class="inner">
                <h4 class="text-bold">{{ sum_remainings }}</h4>

                <p>ເງິນທີ່ຍັງເຫຼືອ</p>
              </div>
              <div class="icon">
                <i class="ion">₭</i>
              </div>
              <a href="#" class="small-box-footer">ລາຍລະອຽດ<i class="fas fa-arrow-circle-right"></i></a>
            </div>
          </div>
          <div class="col-lg-3 col-6">
           
          </div>
          <!-- ./col -->
          <div class="col-lg-3 col-6">
            <!-- small box -->
            <div class="small-box bg-danger">
              <div class="inner">
                <h4>{{ sum_expense_month }}</h4>

                <p>ລາຍຈ່າຍເດືອນນີ້</p>
              </div>
              <div class="icon">
                <i class="ion">₭</i>
              </div>
              <a href="#" class="small-box-footer">ລາຍລະອຽດ <i class="fas fa-arrow-circle-right"></i></a>
            </div>
          </div>
          <div class="col-lg-3 col-6">
            <!-- small box -->
            <div class="small-box bg-success">
              <div class="inner">
                <h4>{{sum_income_month}}</h4>

                <p>ລາຍຮັບເດືອນນີ້</p>
              </div>
              <div class="icon">
                <i class="ion">₭</i>
              </div>
              <a href="#" class="small-box-footer">ລາຍລະອຽດ <i class="fas fa-arrow-circle-right"></i></a>
            </div>
          </div>
          <div class="col-lg-3 col-6">
            <!-- small box -->
            <div class="small-box bg-success">
              <div class="inner">
                <h4 class="text-bold">{{ sum_income_today }}</h4>

                <p>ລາຍຮັບມື້ນີ້</p>
              </div>
              <div class="icon">
                <i class="ion">₭</i>
              </div>
              <a href="#" class="small-box-footer">ລາຍລະອຽດ <i class="fas fa-arrow-circle-right"></i></a>
            </div>
          </div>
          <div class="col-lg-3 col-6">
            <!-- small box -->
            <div class="small-box bg-danger">
              <div class="inner">
                <h4 class="text-bold">{{ sum_expense_today }}</h4>

                <p>ລາຍຈ່າຍມື້ນີ້</p>
              </div>
              <div class="icon">
                <i class="ion">₭</i>
              </div>
              <a href="#" class="small-box-footer">ລາຍລະອຽດ <i class="fas fa-arrow-circle-right"></i></a>
            </div>
          </div>
          <!-- ./col -->
        </div>
        <div class="row">
          <div class="col-12 col-sm-6 col-md-3">
            <div class="info-box">
              <span class="info-box-icon bg-info elevation-1"><i class="fas fa-book"></i></span>

              <div class="info-box-content">
                <span class="info-box-text">ແຜນການທັງໝົດ</span>
                <span class="info-box-number">
                  {{ count_all_plans }}
                </span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
          </div>
          <!-- /.col -->
          <div class="col-12 col-sm-6 col-md-3">
            <div class="info-box mb-3">
              <span class="info-box-icon bg-danger elevation-1"><i class="fas fa-book"></i></span>

              <div class="info-box-content">
                <span class="info-box-text">ແຜນການທີ່ສຳເລັດແລ້ວ</span>
                <span class="info-box-number">{{ count_success_plans }}</span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
          </div>
          <!-- /.col -->

          <!-- fix for small devices only -->
          <div class="clearfix hidden-md-up"></div>

          <div class="col-12 col-sm-6 col-md-3">
            <div class="info-box mb-3">
              <span class="info-box-icon bg-warning elevation-1"><i class="fas fa-book"></i></span>

              <div class="info-box-content">
                <span class="info-box-text">ແຜນການທີ່ບໍ່ທັນສຳເລັດ</span>
                <span class="info-box-number">{{ count_plans_not_success }}</span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
          </div>
          <!-- /.col -->
          <div class="col-12 col-sm-6 col-md-3">
            <div class="info-box mb-3">
              <span class="info-box-icon bg-success elevation-1"><i class="fas fa-table"></i></span>

              <div class="info-box-content">
                <span class="info-box-text">ຈຳນວນມື້</span>
                <span class="info-box-number">{{ count_days }}</span>
              </div>
              <!-- /.info-box-content -->
            </div>
            <!-- /.info-box -->
          </div>
          <!-- /.col -->
        </div>
        <!-- /.row -->
        <!-- Main row -->
        
        <!-- /.row (main row) -->
      </div><!-- /.container-fluid -->
    </section>
    <!-- /.content -->
  </div>
</template>

<script>
import axios from 'axios';
import HeaderComponent from './includes/HeaderComponent.vue';
import SidebarComponent from './includes/SidebarComponent.vue';
export default {
  name: 'DashboardComponent',
  components: {

    HeaderComponent,
    SidebarComponent
  },
  data(){
    return{
      sum_income: 0,
      sum_expense: 0,
      sum_remainings: 0,
      sum_income_today: 0,
      sum_expense_today: 0,
      sum_expense_month: 0,
      sum_income_month: 0,
      count_all_plans: 0,
      count_success_plans: 0,
      count_plans_not_success: 0,
      count_days: 0
    }
  },
  mounted(){
    this.SumALLIncome();
    this.SumALLExpense();
    this.SumALLRemaining();
    this.SumALLIncomeToDay();
    this.SumALLExpenseToDay();
    this.SumALLExpenseMonth();
    this.SumALLIncomeMonth();
    this.CountAllPlan();
    this.CountSuccessPlan();
    this.CountNotSuccessPlan();
    this.CountDaysPlan();
  },
  methods:{
    async SumALLIncome(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/sum-all-income')
      .then(response => {
        this.sum_income = response.data.sum_income;
      })
      .catch(error => {
        console.log("Error", error);
      })
    },
    async SumALLExpense(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/sum-all-expense')
      .then(response => {
        this.sum_expense = response.data.sum_expense;
      })
      .catch(error => {
        console.log("Error", error);
      })
    },
    async SumALLRemaining(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/sum-all-remainings')
      .then(response => {
        this.sum_remainings = response.data.sum_remainings;
      })
      .catch(error => {
        console.log("Error", error);
      })
    }
    ,
    async SumALLIncomeToDay(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/sum-income-today')
      .then(response => {
        this.sum_income_today = response.data.sum_income_today;
      })
      .catch(error => {
        console.log("Error", error);
      })
    },
    async SumALLExpenseToDay(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/sum-expense-today')
      .then(response => {
        this.sum_expense_today = response.data.sum_expense_today;
      })
      .catch(error => {
        console.log("Error", error);
      })
    },
    async SumALLExpenseMonth(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/sum-expense-month')
      .then(response => {
        this.sum_expense_month = response.data.sum_expense_month;
      })
      .catch(error => {
        console.log("Error", error);
      })
    },
    async SumALLIncomeMonth(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/sum-income-month')
      .then(response => {
        this.sum_income_month = response.data.sum_income_month;
      })
      .catch(error => {
        console.log("Error", error);
      })
    },
    async CountAllPlan(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/count-all-plan')
      .then(response => {
        this.count_all_plans = response.data.count_all_plans;
      })
      .catch(error => {
        console.log("Error", error);
      })
    },
    async CountSuccessPlan(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/count-plan-success')
      .then(response => {
        this.count_success_plans = response.data.count_success_plans;
      })
      .catch(error => {
        console.log("Error", error);
      })
    },
    async CountNotSuccessPlan(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/count-plan-not-success')
      .then(response => {
        this.count_plans_not_success = response.data.count_plans_not_success;
      })
      .catch(error => {
        console.log("Error", error);
      })
    },
    async CountDaysPlan(){
      axios.get('https://nodejsbackenddailies-m7t9.onrender.com/api/count-days')
      .then(response => {
        this.count_days = response.data.count_days;
      })
      .catch(error => {
        console.log("Error", error);
      })
    }
  }
  
}
</script>




