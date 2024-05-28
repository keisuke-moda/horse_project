<script setup lang="ts">
const router = useRouter()

const changeRegisterPage = () => {
    router.push('/register-race')
}

const changeDataPage = () => {
    router.push('/data')
}
</script>

<template>
    <div>タイトルページ</div>
    <button @click="changeRegisterPage()">登録画面へ</button>
    <button @click="changeDataPage()">データ分析画面</button>
</template>

<style scoped></style>