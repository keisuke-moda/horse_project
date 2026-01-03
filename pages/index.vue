<script setup lang="ts">
const router = useRouter()
</script>

<template>
    <div class="title">タイトルページ</div>
    <button @click="router.push('/register-race')">登録画面へ</button>
    <button @click="router.push('/data')">データ分析画面</button>
    <button @click="router.push('/result')">過去の結果一覧</button>
</template>

<style scoped>
.title {
    display: flex;
    flex-direction: column;
}
</style>