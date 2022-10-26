<template>
  <div>
    <header class="p-5 w-full text-center bg-black fixed text-white">
      <h1 class="font-semibold text-3xl">GetJadwal</h1>
    </header>
    <div class="h-screen w-full bg-slate-200 flex justify-center">
      <!-- card start -->
      <div class="px-10 py-5 bg-white w-96 h-80 mt-48 rounded-md shadow-xl">
        <h1 class="text-center font-semibold text-2xl mb-10 mt-5">Check In</h1>
        <label for="email" class="block">Email</label>
        <input
          type="email"
          name="email"
          id="email"
          class="bg-slate-100 rounded-md block border-spacing-1 mb-5 p-3 w-full border-2 border-slate-300 outline-2 focus:outline-pink-400"
          placeholder="masukan alamat email anda"
          required
        />
        <font-awesome-icon icon="fa-solid fa-user-secret" />
        <button
          class="rounded-full bg-pink-400 hover:bg-pink-500 active:bg-pink-600 text-white px-2 py-4 w-full font-bold"
        >
          Mulai Sesi
        </button>
      </div>
      <!-- card end -->
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
};
</script>
