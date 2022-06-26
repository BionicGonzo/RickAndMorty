<template>
    <div class="col-md-8 mx-auto">
        <div v-for="(personaje, index) in data" :key="index" class="card bg-transparent border-success rounded-3 mb-3 p-3">
            <div class="row">

                <div class="col-2">
                    <img :src="personaje.image" :alt="personaje.name" class="img-fluid rounded-circle">
                </div>

                <div class="col-10">
                    <h2 class="text-start ms-3 fw-bold text-light">{{personaje.name}}</h2>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Personaje",
    props: ['data'],
    data() {
        return {

        }
    },
}
</script>

<style scoped>

</style>