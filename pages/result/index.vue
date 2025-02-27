<script setup lang="ts">
const router = useRouter()
</script>

<template>
    <div>
        テスト。過去の馬券結果一覧を確認したい。
    </div>
    <button @click="router.go(-1)">戻る</button>
</template>