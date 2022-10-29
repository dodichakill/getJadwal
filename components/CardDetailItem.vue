<template>
  <!-- card item start -->
  <div class="card-item-container w-full mb-5" data-cy="card-item-title">
    <div
      class="px-5 py-3 rounded-lg flex bg-white items-center justify-between mt-2 shadow-md"
    >
      <div class="item-name text-xl text-slate-600">{{ nama_mk }}</div>
      <div class="action text-xl">
        <button
          class="p-2 text-slate-400 hover:text-slate-500"
          title="edit jadwal"
          data-cy="card-item-edit"
          @click="show_edit_event"
        >
          <font-awesome-icon icon="fa-solid fa-pen-to-square" />
        </button>
        <button
          class="p-2 text-slate-400 hover:text-red-500"
          title="hapus jadwal"
          data-cy="card-item-delete"
          @click="show_delete_event"
        >
          <font-awesome-icon icon="fa-solid fa-trash" />
        </button>
      </div>
    </div>
  </div>
  <!-- card item end -->
</template>

<script>
export default {
  props: ["nama_mk", "show_edit_event", "show_delete_event"],
};
</script>
