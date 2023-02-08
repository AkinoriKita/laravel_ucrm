<script setup>
import { router } from '@inertiajs/vue3'

defineProps({
    id : String,
    blog: Object
})
const deleteComfirm = id => {
    router.delete(`/inertia/${id}`, {
        onBefore: () => confirm('本当に削除しますか？')
    })
}

</script>

<template>
    {{ id }}<br>
    {{ blog.title }}<br>
    <button @click="deleteComfirm(blog.id)">Delete</button>
</template>