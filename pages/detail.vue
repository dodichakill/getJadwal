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
          <a href="#" class="text-2xl">
            <font-awesome-icon
              icon="fa-solid fa-chevron-left"
              data-cy="btn-back"
            />
            <span class="day ml-2 font-semibold" data-cy="detail-title"
              >Senin</span
            >
          </a>
          <button
            class="rounded-full bg-pink-400 hover:bg-pink-500 active:bg-pink-600 text-white h-14 px-4 py-4 font-bold shadow-xl shadow-pink-300"
            data-cy="btn-create-schedule"
          >
            <font-awesome-icon icon="fa-solid fa-plus" />
            <span class="ml-2">Tambah Mata Kuliah</span>
          </button>
        </div>

        <!-- image empty start -->
        <div class="flex">
          <img
            src="todo-empty-state.png"
            alt="image-todo-empty"
            class="w-1/2 xl:w-1/3 m-auto mt-10"
            data-cy="todo-empty-state"
          />
        </div>
        <!-- image empty end -->
      </div>
    </div>
  </div>
</template>
