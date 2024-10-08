<template>
  <!-- Main Sidebar Container -->
  <aside class="main-sidebar sidebar-dark-primary elevation-4">
    <!-- Brand Logo -->
    <a href="index3.html" class="brand-link">
      <img src="dist/img/ewallet.png" alt="AdminLTE Logo" class="brand-image img-circle elevation-3" style="opacity: .8">
      <span class="brand-text font-weight-light">ລະບົບການເງິນ</span>
    </a>

    <!-- Sidebar -->
    <div class="sidebar">
      <!-- Sidebar user panel (optional) -->
      <div class="user-panel mt-3 pb-3 mb-3 d-flex">
        <div class="image">
          <img src="dist/img/avatar5.png" class="img-circle elevation-2" alt="User Image">
        </div>
        <div class="info">
          <a href="#" class="d-block">ທ ສຸກທັນວາ ມ້າວປະເສີດ</a>
        </div>
      </div>

      

      <!-- Sidebar Menu -->
      <nav class="mt-2">
        <ul class="nav nav-pills nav-sidebar flex-column" data-widget="treeview" role="menu" data-accordion="false">
          <!-- Add icons to the links using the .nav-icon class
               with font-awesome or any other icon font library -->
          <li class="nav-item menu-open">
            <router-link to="/dashboard" href="#" class="nav-link">
              <i class="nav-icon fas fa-tachometer-alt"></i>
              <p class="text-bold">
                ໜ້າຫຼັກ
              </p>
            </router-link>
          </li>
          <li class="nav-item menu-open">
            <router-link to="/admin" href="#" class="nav-link">
              <i class="nav-icon fas fa-user"></i>
              <p class="text-bold">
                ແອັດມິນ
                
              </p>
            </router-link>
          </li>
          <li class="nav-item menu-open">
            <router-link to="/daily" href="#" class="nav-link">
              <i class="nav-icon fas fa-user"></i>
              <p class="text-bold">
                ປຶ້ມບັນທຶກປະຈໍາວັນ
                
              </p>
            </router-link>
          </li>
          <li class="nav-item menu-open">
            <router-link to="/modules" href="#" class="nav-link">
              <i class="nav-icon fas fa-book"></i>
              <p class="text-bold">
                modules (ໂມດູລ)
                
              </p>
            </router-link>
          </li>
          <li class="nav-item menu-open">
            <router-link to="/notes" href="#" class="nav-link">
              <i class="nav-icon fas fa-book-open"></i>
              <p class="text-bold">
                Notes (ການບັນທືກ)
                
              </p>
            </router-link>
          </li>

          <li class="nav-item menu-open">
            <router-link to="/income_expense" href="#" class="nav-link">
              <i class="nav-icon fas">K</i>
              <p class="text-bold">
                ລາຍຮັບ/ລາຍຈ່າຍ
                
              </p>
            </router-link>
          </li>
          <li class="nav-item menu-open">
            <router-link to="/plan" href="#" class="nav-link">
              <i class="nav-icon fas fa-book-open"></i>
              <p class="text-bold">
                ແຜນການ
                
              </p>
            </router-link>
          </li>
          <li class="nav-item menu-open">
            <router-link to="/school-table" href="#" class="nav-link">
              <i class="nav-icon fas fa-table"></i>
              <p class="text-bold">
                ຕາຕະລາງ
                
              </p>
            </router-link>
          </li>
          <li class="nav-item menu-open">
            <button @click="ConfirmLogout" class="nav-link" style="text-align: start;">
              <i class="nav-icon fas fa-power-off"></i>
              <p class="text-bold">
                ອອກຈາກລະບົບ
                
              </p>
            </button>
          </li>
        </ul>
      </nav>
      <!-- /.sidebar-menu -->
    </div>
    <!-- /.sidebar -->
  </aside>
</template>

<script>
import Swal from 'sweetalert2'
export default {
  name: 'SidebarComponent',

  methods:{
    async ConfirmLogout(){
        Swal.fire({
          title: 'ອອກຈາກລະບົບແທ້ ຫຼື ບໍ່?',
          text: 'ທ່ານ ແນ່ໃຈບໍ່ ທີ່ຈະອອກຈະລະບົບ: ',
          icon: 'warning',
          showCancelButton: true,
          cancelButtonText: 'ຍົກເລີກ',
          confirmButtonColor: '#d33',
          cancelButtonColor: '#3085d6',
          confirmButtonText: 'ຍືນຍັນ!'
        }).then((result => {
          if(result.isConfirmed){
            this.HandleLogout();
          }
        }))
    },

    async HandleLogout(){
      localStorage.removeItem('token');
      this.ShowLogoutMessage();
      this.$router.push('/login');

    },
    async ShowLogoutMessage(){
      Swal.fire({
        title: "ສຳເລັດ",
        text: "ອອກຈາກລະບົບສໍາເລັດ",
        icon: "success",
        timer: 2000,
        timerProgressBar: true,
        didOpen: () => {
          Swal.showLoading();
        }
      })
    },
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>