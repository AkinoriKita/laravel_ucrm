<script setup>
import { Link } from '@inertiajs/vue3';
import { ref } from "vue";

const newTitle = ref('')
const newContent = ref('')
</script>

<template>
Inertiaテストです。<br>
<a href="/">aタグ</a><br>
<Link href="/">Link</Link><br>
<Link :href="route('inertia.index')">namae tuki route</Link><br>
<Link :href="route('inertia.show', { id: 1 })">route para test</Link>

<div class="mb-8"></div>
<input type="text" name="newTitle" v-model="newTitle"><br>
<input type="text" name="newContent" v-model="newContent"><br>
<Link as="button" method="POST" :href="route('inertia.store')"
:data="{ 
    title: newTitle,
    content: newContent
 }">DB STORE</Link>
</template>