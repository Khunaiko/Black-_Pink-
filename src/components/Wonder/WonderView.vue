<template>
    <div class="container mt-4">
        <div class="row">
            <div class="col-md-3 mb-5 justify-content-md-start" v-for="item in allWonders" :key="item.id">
                <div class="card shadow p-0">
                    <img :src="item.imageUrl" class="card-img-top" height="450px" alt="wonders">
                    <div class="card-body">
                        <h5 class="card-title">{{ item.name }}</h5>
                        <p class="card-text"> YG Entertainment {{ item.location }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import axios from 'axios'
import { onMounted,ref } from 'vue';

const allWonders = ref([]);

onMounted(() => {
    axios.get(`http://localhost:8080/BlackPink`)
        .then((response) => {
            // console.log(response.data)
            allWonders.value = response.data
        })
})

</script>

<style lang="scss" scoped></style>