<script setup lang="ts">
const router = useRouter()
const returnPage = () => {
    router.go(-1)
}
</script>

<template>
    <div>
        テスト。過去のレース結果から絞り込みできる機能を付けたい
    </div>
    <button @click="returnPage()">戻る</button>
</template>