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
    <div class="min-h-screen h-auto relative w-full bg-slate-200">
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
        <div class="card-container flex gap-4 w-full">
          <CardJadwal hari="Senin" jumlahmatkul="3"></CardJadwal>
          <CardJadwal hari="Selasa" jumlahmatkul="3"></CardJadwal>
          <CardJadwal hari="Rabu" jumlahmatkul="3"></CardJadwal>
          <CardJadwal hari="Kamis" jumlahmatkul="3"></CardJadwal>
          <CardJadwal hari="Jumat" jumlahmatkul="3"></CardJadwal>
        </div>
        <!-- card jadwal end -->
      </div>
    </div>
    <!-- modal start-->
    <div
      class="modal-back absolute top-0 left-0 right-0 bottom-0 bg-slate-700/50 min-h-screen flex"
    >
      <!-- modal content start -->
      <div class="p-8 bg-white w-96 m-auto h-96 rounded-lg" data-cy="form-add">
        <h2 class="text-center mb-5 text-2xl font-semibold">
          Buat Jadwal Kuliah
        </h2>
        <label
          for="matakuliah"
          class="font-semibold border-t-2 w-full block pt-3"
          >Mata Kuliah</label
        >
        <input
          type="text"
          name="matakuliah"
          data-cy="form-matkul"
          id="matakuliah"
          class="outline block outline-1 px-3 py-2 rounded-lg outline-slate-300 mt-1 w-full mb-5 focus:outline-2 focus:outline-pink-400"
          placeholder="Masukan Mata Kuliah"
        />
        <label for="day" class="font-semibold">Pilih Hari</label>
        <!-- <input
          type="se"
          name="pilihhari"
          data-cy="form-day"
          id="pilihhari"
          class="outline block outline-1 px-3 py-2 rounded-lg outline-slate-300 mt-1 w-full"
          placeholder="Pilih Hari"
        /> -->
        <select
          name="day"
          id="day"
          class="block px-3 py-2 w-full bg-white border-2 rounded-lg cus:outline-2 focus:outline-pink-400"
          data-cy="form-day"
          placeholder="Pilih Hari"
        >
          <option value="Senin">Senin</option>
          <option value="Selasa">Selasa</option>
          <option value="Rabu">Rabu</option>
          <option value="Kamis">Kamis</option>
          <option value="Jumat">Jumat</option>
        </select>

        <div
          class="mt-6 text-white border-t-2 font-semibold flex justify-between"
        >
          <button
            class="px-6 py-2 bg-white border-2 border-red-400 text-red-400 rounded-full mt-5 shadow-xl shadow-red-300"
            data-cy="close-modal"
          >
            <font-awesome-icon icon="fa-solid fa-circle-xmark" />
            <span class="ml-2">Batalkan</span>
          </button>
          <button
            class="px-6 py-2 border-pink-400 border-2 bg-pink-400 rounded-full mt-5 shadow-xl shadow-pink-300"
            data-cy="btn-submit"
          >
            <font-awesome-icon icon="fa-solid fa-floppy-disk" />
            <span class="ml-2">Simpan</span>
          </button>
        </div>
      </div>
      <!-- modal content end -->
    </div>
    <!-- modal end-->
  </div>
</template>
