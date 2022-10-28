<template>
  <div>
    <header class="p-5 w-full text-center bg-black fixed text-white">
      <h1 class="font-semibold text-3xl">GetJadwal</h1>
    </header>
    <div class="h-screen w-full bg-slate-200 flex justify-center">
      <!-- card start -->
      <div class="px-10 py-5 bg-white w-96 h-80 mt-48 rounded-md shadow-lg">
        <h1
          class="text-center font-semibold text-2xl mb-10 mt-5"
          data-cy="text-login"
        >
          Check In
        </h1>
        <label for="email" class="block">Email</label>
        <input
          type="email"
          name="email"
          id="email"
          class="bg-slate-100 rounded-md block border-spacing-1 mb-2 p-3 w-full border-2 border-slate-300 outline-2 focus:outline-pink-400"
          placeholder="masukan alamat email anda"
          required
          data-cy="input-email"
          v-model="email"
          @change="validateEmail()"
        />
        <div class="if" v-if="error">
          <p class="text-red-500">
            <font-awesome-icon icon="fa-solid fa-circle-info" />
            <span class="ml-1" data-cy="error-email"
              >format email tidak sesuai</span
            >
          </p>
        </div>
        <button
          class="rounded-full mt-3 shadow-lg shadow-pink-300 bg-pink-400 hover:bg-pink-500 active:bg-pink-600 text-white px-2 py-4 w-full font-bold"
          data-cy="btn-login"
        >
          Mulai Sesi
        </button>
      </div>
      <!-- card end -->
    </div>
  </div>
</template>

<script>
var axios = require("axios");
var data = '{\r\n    "email": "john@email.com"\r\n}';

var config = {
  method: "post",
  url: "https://getjadwal.api.devcode.gethired.id/checkin",
  headers: {},
  data: data,
};

export default {
  name: "IndexPage",
  data() {
    return {
      error: false,
      email: "",
    };
  },
  methods: {
    validateEmail() {
      const elmEmail = document.querySelector('input["email"]');
      if (
        /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(elmEmail.value)
      ) {
        this.error = false;
      } else {
        this.error = true;
      }
    },
  },
};
</script>
