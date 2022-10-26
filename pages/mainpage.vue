<template>
  <div>
    <header class="p-5 w-full bg-black text-white">
      <div class="container flex justify-between m-auto">
        <h1 class="font-semibold text-3xl">GetJadwal</h1>
        <button
          class="btn px-4 py-2 bg-pink-400 rounded-lg font-semibold"
          data-cy="btn-logout"
        >
          Check Out | Yourmail@mail.com
        </button>
      </div>
    </header>
    <div class="min-h-screen relative w-full bg-slate-200">
      <div class="container m-auto">
        <!-- btn create schedule start -->
        <button
          class="rounded-full bg-pink-400 hover:bg-pink-500 active:bg-pink-600 text-white h-14 px-4 py-4 font-bold mt-12 mb-10 shadow-xl shadow-pink-300"
          data-cy="btn-create-schedule"
        >
          <font-awesome-icon icon="fa-solid fa-plus" />
          <span class="ml-2">Buat Jadwal Kuliah</span>
        </button>
        <!-- btn create schedule end -->

        <!-- card jadwal start -->
        <CardJadwal hari="senin" jumlahmatkul="3"></CardJadwal>
        <!-- card jadwal end -->
      </div>
    </div>
  </div>
</template>
