<template>
  <div>
    <header class="p-5 w-full bg-black text-white">
      <div class="container flex justify-between m-auto">
        <h1 class="font-semibold text-3xl">GetJadwal</h1>
        <button
          class="btn px-4 py-2 bg-pink-400 rounded-lg font-semibold"
          data-cy="btn-logout"
          @click="logout"
        >
          Check Out | {{ email }}
        </button>
      </div>
    </header>
    <div class="min-h-screen h-auto relative w-full bg-slate-200">
      <div class="container m-auto">
        <!-- btn create schedule start -->
        <button
          class="rounded-full bg-pink-400 hover:bg-pink-500 active:bg-pink-600 text-white h-14 px-4 py-4 font-bold mt-12 mb-10 shadow-lg shadow-pink-300"
          data-cy="btn-create-schedule"
          @click="showModalBox"
        >
          <font-awesome-icon icon="fa-solid fa-plus" />
          <span class="ml-2">Buat Jadwal Kuliah</span>
        </button>
        <!-- btn create schedule end -->

        <!-- card jadwal start -->
        <div class="card-container flex gap-4 w-full">
          <CardJadwal hari="Senin" :jumlahmk="jumlahMKSenin"></CardJadwal>
          <CardJadwal hari="Selasa" :jumlahmk="jumlahMKSelasa"></CardJadwal>
          <CardJadwal hari="Rabu" :jumlahmk="jumlahMKRabu"></CardJadwal>
          <CardJadwal hari="Kamis" :jumlahmk="jumlahMKKamis"></CardJadwal>
          <CardJadwal hari="Jumat" :jumlahmk="jumlahMKJumat"></CardJadwal>
        </div>
        <!-- card jadwal end -->
      </div>
    </div>
    <HomeModalBoxAdd :state_event="isShowModalBox" :hide_event="hideModalBox" />
  </div>
</template>

<script>
import HomeModalBoxAdd from "~/components/HomeModalBoxAdd.vue";

const userEmail = process.server ? "" : localStorage.getItem("USER_EMAIL");

// ketika script diload di sisi client
let backToLogin;
if (process.client) {
  backToLogin = () => {
    window.location.replace("/");
  };
  // jika email tidak terdaftar maka kembali ke halaman index/login
  if (userEmail === "") {
    backToLogin();
  }
}

export default {
  data() {
    return {
      isShowModalBox: false,
      email: userEmail,
      scheduleSenin: this.getAllSchedule().Monday,
      jumlahMKSenin: 0,
      jumlahMKSelasa: 0,
      jumlahMKRabu: 0,
      jumlahMKKamis: 0,
      jumlahMKJumat: 0,
    };
  },
  mounted() {
    // if (process.client) {
    //   this.getAllSchedule();
    // }
  },
  methods: {
    async getAllSchedule() {
      await this.$axios
        .$get("schedule?email=" + localStorage.getItem("USER_EMAIL"))
        .then((response) => {
          const result = response.data;
          this.jumlahMKSenin = result.monday;
          this.jumlahMKSelasa = result.tuesday;
          this.jumlahMKRabu = result.wednesday;
          this.jumlahMKKamis = result.thursday;
          this.jumlahMKJumat = result.friday;
        });
    },
    showModalBox() {
      this.isShowModalBox = true;
    },
    hideModalBox() {
      this.isShowModalBox = false;
    },
    logout() {
      localStorage.clear();
      backToLogin();
    },
  },
  components: { HomeModalBoxAdd },
};
</script>
