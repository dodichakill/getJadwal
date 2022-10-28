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
          <div class="text-2xl">
            <nuxt-link to="/home">
              <font-awesome-icon
                icon="fa-solid fa-chevron-left"
                data-cy="btn-back"
              />
              <span class="day ml-2 font-semibold" data-cy="detail-title">{{
                $route.params.day
              }}</span>
            </nuxt-link>
          </div>
          <button
            class="rounded-full bg-pink-400 hover:bg-pink-500 active:bg-pink-600 text-white h-14 px-4 py-4 font-bold shadow-lg shadow-pink-300"
            data-cy="btn-create-schedule"
            @click="showAddModalBox"
          >
            <font-awesome-icon icon="fa-solid fa-plus" />
            <span class="ml-2">Tambah Mata Kuliah</span>
          </button>
        </div>

        <!-- image empty start -->
        <div class="flex hidden">
          <img
            src="~/assets/todo-empty-state.png"
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
                @click="showEditModalBox"
              >
                <font-awesome-icon icon="fa-solid fa-pen-to-square" />
              </button>
              <button
                class="p-2 text-slate-400 hover:text-red-500"
                title="hapus jadwal"
                data-cy="card-item-delete"
                @click="showDeleteModalBox"
              >
                <font-awesome-icon icon="fa-solid fa-trash" />
              </button>
            </div>
          </div>
        </div>
        <!-- card item end -->
      </div>
    </div>

    <DetailModalBoxAdd
      :state_event="isShowAddModalBox"
      :hide_event="hideAddModalBox"
    />

    <DetailModalBoxEdit
      :state_event="isShowEditModalBox"
      :hide_event="hideEditModalBox"
    />

    <DetailModalBoxDelete
      :state_event="isShowDeleteModalBox"
      :hide_event="hideDeleteModalBox"
    />
    <!-- toast start -->
    <p
      class="toast px-3 py-2 w-72 m-auto rounded-lg bg-green-400 inlineblock absolute top-16 left-0 right-0 shadow shadow-green-200 hidden"
    >
      <font-awesome-icon icon="fa-solid fa-circle-check" class="ml-2" />
      <span class="ml-2"> mata kuliah berhasil dihapus </span>
    </p>
    <!-- toast end -->
  </div>
</template>

<script>
import DetailModalBoxDelete from "~/components/DetailModalBoxDelete.vue";

export default {
  data() {
    return {
      isShowEditModalBox: false,
      isShowAddModalBox: false,
      isShowDeleteModalBox: false,
      isShowToast: false,
    };
  },
  methods: {
    showAddModalBox() {
      this.isShowAddModalBox = true;
    },
    showEditModalBox() {
      this.isShowEditModalBox = true;
    },
    showDeleteModalBox() {
      this.isShowDeleteModalBox = true;
    },
    showToast() {
      this.isShowToast = true;
    },
    hideAddModalBox() {
      this.isShowAddModalBox = false;
    },
    hideEditModalBox() {
      this.isShowEditModalBox = false;
    },
    hideDeleteModalBox() {
      this.isShowDeleteModalBox = false;
    },
    hideToast() {
      this.isShowToast = false;
    },
  },
  components: { DetailModalBoxDelete },
};
</script>
