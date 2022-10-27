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
        <div
          class="flex justify-between pt-8 pb-8 items-center"
          style="border-bottom: 2px solid rgba(0, 0, 0, 0.15)"
        >
          <a href="/main" class="text-2xl">
            <font-awesome-icon
              icon="fa-solid fa-chevron-left"
              data-cy="btn-back"
            />
            <span class="day ml-2 font-semibold" data-cy="detail-title"
              >Senin</span
            >
          </a>
          <button
            class="rounded-full bg-pink-400 hover:bg-pink-500 active:bg-pink-600 text-white h-14 px-4 py-4 font-bold shadow-lg shadow-pink-300"
            data-cy="btn-create-schedule"
          >
            <font-awesome-icon icon="fa-solid fa-plus" />
            <span class="ml-2">Tambah Mata Kuliah</span>
          </button>
        </div>

        <!-- image empty start -->
        <div class="flex hidden">
          <img
            src="todo-empty-state.png"
            alt="image-todo-empty"
            class="w-1/2 xl:w-1/3 m-auto mt-10"
            data-cy="todo-empty-state"
          />
        </div>
        <!-- image empty end -->

        <!-- card item start -->
        <div class="card-item-container w-full mt-10" data-cy="card-item-title">
          <div
            class="px-5 py-3 rounded-lg flex bg-white items-center justify-between mt-2 shadow-md"
          >
            <div class="item-name text-xl text-slate-600">Statistika cuy</div>
            <div class="action text-xl">
              <button
                class="p-2 text-slate-400 hover:text-slate-500"
                title="edit jadwal"
                data-cy="card-item-edit"
              >
                <font-awesome-icon icon="fa-solid fa-pen-to-square" />
              </button>
              <button
                class="p-2 text-slate-400 hover:text-red-500"
                title="hapus jadwal"
                data-cy="card-item-delete"
              >
                <font-awesome-icon icon="fa-solid fa-trash" />
              </button>
            </div>
          </div>
        </div>
        <!-- card item end -->
      </div>
    </div>

    <!-- modal add jadwal start-->
    <div
      class="modal-back absolute top-0 left-0 right-0 bottom-0 bg-slate-700/50 min-h-screen flex hidden"
    >
      <!-- modal content start -->
      <form
        class="p-8 bg-white w-96 m-auto h-72 rounded-lg"
        data-cy="form-add"
        name="add"
      >
        <h2 class="text-center mb-5 text-2xl font-semibold">
          Buat Jadwal Kuliah
        </h2>
        <label
          for="add-matkul"
          class="font-semibold border-t-2 w-full block pt-3"
          >Mata Kuliah</label
        >
        <input
          type="text"
          name="add-matkul"
          data-cy="form-matkul"
          id="add-matkul"
          class="outline block outline-1 px-3 py-2 rounded-lg outline-slate-300 mt-1 w-full mb-5 focus:outline-2 focus:outline-pink-400"
          placeholder="Masukan Mata Kuliah"
        />

        <div
          class="mt-6 text-white border-t-2 font-semibold flex justify-between"
        >
          <button
            class="px-6 py-2 bg-white border-2 border-red-400 text-red-400 rounded-full mt-5 shadow-lg shadow-red-300"
            data-cy="close-modal"
          >
            <font-awesome-icon icon="fa-solid fa-circle-xmark" />
            <span class="ml-2">Batalkan</span>
          </button>
          <button
            class="px-6 py-2 border-pink-400 border-2 bg-pink-400 rounded-full mt-5 shadow-lg shadow-pink-300"
            data-cy="btn-submit"
            type="submit"
          >
            <font-awesome-icon icon="fa-solid fa-floppy-disk" />
            <span class="ml-2">Simpan</span>
          </button>
        </div>
      </form>
      <!-- modal content end -->
    </div>
    <!-- modal add jadwal end-->

    <!-- modal edit jadwal start-->
    <div
      class="modal-back absolute top-0 left-0 right-0 bottom-0 bg-slate-700/50 min-h-screen flex hidden"
    >
      <!-- modal content start -->
      <form
        class="p-8 bg-white w-96 m-auto h-72 rounded-lg"
        data-cy="form-edit"
        name="edit"
      >
        <h2 class="text-center mb-5 text-2xl font-semibold">
          Edit Jadwal Kuliah
        </h2>
        <label
          for="edit-matkul"
          class="font-semibold border-t-2 w-full block pt-3"
          >Mata Kuliah</label
        >
        <input
          type="text"
          name="edit-matkul"
          data-cy="form-matkul"
          id="edit-matkul"
          class="outline block outline-1 px-3 py-2 rounded-lg outline-slate-300 mt-1 w-full mb-5 focus:outline-2 focus:outline-pink-400"
          value="Statistika"
        />

        <div
          class="mt-6 text-white border-t-2 font-semibold flex justify-between"
        >
          <button
            class="px-6 py-2 bg-white border-2 border-red-400 text-red-400 rounded-full mt-5 shadow-lg shadow-red-300"
            data-cy="close-modal"
          >
            <font-awesome-icon icon="fa-solid fa-circle-xmark" />
            <span class="ml-2">Batalkan</span>
          </button>
          <button
            class="px-6 py-2 border-pink-400 border-2 bg-pink-400 rounded-full mt-5 shadow-lg shadow-pink-300"
            data-cy="btn-submit"
            type="submit"
          >
            <font-awesome-icon icon="fa-solid fa-floppy-disk" />
            <span class="ml-2">Simpan</span>
          </button>
        </div>
      </form>
      <!-- modal content end -->
    </div>
    <!-- modal edit jadwal end-->

    <!-- modal hapus jadwal start-->
    <div
      class="modal-back absolute top-0 left-0 right-0 bottom-0 bg-slate-700/50 min-h-screen flex"
    >
      <!-- modal content start -->
      <form
        class="p-8 bg-white w-96 m-auto h-72 rounded-lg flex justify-center items-center flex-col"
        data-cy="form-edit"
        name="edit"
      >
        <div
          class="logo px-5 py-4 w-16 rounded-full h-16 bg-red-400 text-3xl text-white flex justify-center items-center"
        >
          <font-awesome-icon icon="fa-solid fa-trash-can" class="m-auto" />
        </div>
        <h2 class="text-center mt-5 mb-5 text-2xl font-semibold">
          Hapus Mata Kuliah
        </h2>
        <p class="text-center text-slate-400">
          Apakah anda yakin ingin menghapus Statistika
        </p>

        <div class="text-white font-semibold flex justify-between w-full">
          <button
            class="px-6 py-2 bg-white border-2 border-red-400 text-red-400 rounded-full mt-5 shadow-lg shadow-red-300"
            data-cy="close-modal"
          >
            <font-awesome-icon icon="fa-solid fa-circle-xmark" />
            <span class="ml-2">Batalkan</span>
          </button>
          <button
            class="px-6 py-2 border-pink-400 border-2 bg-pink-400 rounded-full mt-5 shadow-lg shadow-pink-300"
            data-cy="btn-submit"
            type="submit"
          >
            <font-awesome-icon icon="fa-solid fa-floppy-disk" />
            <span class="ml-2">Simpan</span>
          </button>
        </div>
      </form>
      <!-- modal content end -->
    </div>
    <!-- modal edit jadwal end-->
  </div>
</template>
