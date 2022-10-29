<template>
  <div
    class="modal-back fixed top-0 left-0 right-0 bottom-0 bg-slate-700/50 min-h-screen flex ease-in duration-100"
    v-if="state_event"
  >
    <!-- modal content start -->
    <form class="p-8 bg-white w-96 m-auto h-96 rounded-lg" data-cy="form-add">
      <h2 class="text-center mb-5 text-2xl font-semibold">
        Buat Jadwal Kuliah
      </h2>
      <label for="matkul" class="font-semibold border-t-2 w-full block pt-3"
        >Mata Kuliah</label
      >
      <input
        type="text"
        name="matkul"
        data-cy="form-matkul"
        id="matkul"
        class="outline block outline-1 px-3 py-2 rounded-lg outline-slate-300 mt-1 w-full mb-5 focus:outline-2 focus:outline-pink-400"
        placeholder="Masukan Mata Kuliah"
      />
      <label for="day" class="font-semibold">Pilih Hari</label>
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
          class="px-6 py-2 bg-white border-2 border-red-400 text-red-400 rounded-full mt-5 shadow-lg shadow-red-300"
          data-cy="close-modal"
          @click="hide_event"
        >
          <font-awesome-icon icon="fa-solid fa-circle-xmark" />
          <span class="ml-2">Batalkan</span>
        </button>
        <button
          class="px-6 py-2 cursor-not-allowed border-pink-400 border-2 bg-pink-400 rounded-full mt-5 shadow-lg shadow-pink-300"
          data-cy="btn-submit"
        >
          <font-awesome-icon icon="fa-solid fa-floppy-disk" />
          <span class="ml-2">Simpan</span>
        </button>
      </div>
    </form>
    <!-- modal content end -->
  </div>
  <!-- modal end-->
</template>

<script>
export default {
  data() {
    return {};
  },
  props: ["state_event", "hide_event"],
};
</script>
