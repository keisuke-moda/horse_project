<script setup lang="ts">
import axios, { formToJSON } from 'axios';

const raceName = ref("")
const favorite = ref("")
const howToBuy = ref("")
const bet = ref("")
const returnPay = ref("")

const router = useRouter()
const returnPage = () => {
    router.go(-1)
}

const registerRaceResult = (raceName: string, favorite: string, howToBuy: string, bet: string, returnPay: string) => {
    const instance = axios.create({
        baseURL: 'http://localhost:8080'
    })

    instance.post('/register-race', {
        "raceName": raceName,
        "favorite": favorite,
        "howToBuy": howToBuy,
        "bet": bet,
        "returnPay": returnPay,
    })
        .then((response) => {
            console.log(response)
        })
        .catch((error) => {
            console.log(error)
        })
}
</script>

<template>
    <div class="title">
        <button @click="registerRaceResult(raceName, favorite, howToBuy, bet, returnPay)"
            class="button">馬券登録ボタン</button>
        <input v-model="raceName" placeholder="購入レース">
        <p>購入レース名：{{ raceName }}</p>
        <input v-model="favorite" placeholder="本命馬">
        <p>本命馬：{{ favorite }}</p>
        <input v-model="howToBuy" placeholder="買い目">
        <p>買い目：{{ howToBuy }}</p>
        <input v-model="bet" placeholder="bet">
        <p>かけ金：{{ bet }}</p>
        <input v-model="returnPay" placeholder="return">
        <p>返却：{{ returnPay }}</p>
        <button @click="returnPage()">戻る</button>
    </div>
</template>

<style scoped>
.title {
    display: flex;
    flex-direction: column;
    width: 200px;
}

.button {
    margin-bottom: 16px
}
</style>