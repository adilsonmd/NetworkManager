<script setup>
import Navbar from "../components/Navbar.vue";
import { onMounted, ref } from "vue";

const showDetails = ref(false);

let openModal = () => {

    showDetails.value = true;

};

let closeModal = () => {
    const modal = document.getElementById("modal");
    modal.close();
};

onMounted(() => {
    const listItems = document.querySelectorAll(".list-item");

    listItems.forEach(item => {
        item.addEventListener("click", openModal);
    });
});

</script>

<template>
    <!-- container -->
    <div class="grid-template gap-2">
        <div class="dashboard-item">

            <div class="dashboard-item__header">
                <h3 class="text-muted">VLANS</h3>
                <div class="dashboard-item__controls">
                    <button class="btn btn-dark">
                        <i class="bi bi-arrow-clockwise"></i>
                    </button>
                    <button class="btn btn-dark">
                        <i class="bi bi-list"></i>
                        <!-- <i class="bi bi-triangle-fill"></i> -->
                    </button>
                    <!-- FAZER COM QUE MONSTRE UM PANEL FLUTUANTE COM AS POOLS -->
                </div>
            </div>

            <div class="dashboard-item__body" v-show="showDetails">
                <div class="">
                    <p>Embraport</p>
                    <div>
                        <ul class="list">
                            <li class="list-item">VLAN-01</li>
                            <li class="list-item">VLAN-02</li>
                            <li class="list-item">VLAN-03</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>

        <div id="modal" class="">
            <div>
                <div class="d-flex">
                    <p>IP Address</p>
                    <p>96.45.45.28</p>
                </div>
                <button @click="closeModal" class="btn btn-dark">Fechar</button>
            </div>
        </div>
    </div>
</template>

<style scoped>
.grid-template {
    gap: 1rem;
    grid-template-columns: repeat(1, 1fr);
}

.dashboard-item {
    padding: 1rem;

    min-height: 300px;
    border-radius: 25px;
    border: 1px solid #c5cbd8;
}

.dashboard-item__header {
    display: flex;
    justify-content: space-between;
}

.list {
    list-style: none;
}

.list-item {
    cursor: pointer;
}

.list-item:hover {
    background-color: #3f474f;
}

.modal {
    border-radius: 0.15rem;
    border: 1px solid #2b3030;
}
</style>