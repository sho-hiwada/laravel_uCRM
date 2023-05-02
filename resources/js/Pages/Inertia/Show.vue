<script setup>
import { Inertia } from '@inertiajs/inertia'

defineProps({
  id : String,
  blog: Object
})

const deleteConfirm = (id) => {
  // console.log(id)
  Inertia.delete(`/inertia/${id}`, {
    onBefore: () => confirm('本当に削除してもよろしいですか？')
  })
}

</script>

<template>
  パラメータの値は{{ id }}です。<br>
  {{ blog.title }}
  <button @click="deleteConfirm(blog.id)">削除</button>
</template>