<template>
    <nav class="nav">
        <ul class="navbar-list d-flex justify-content-between">
            <li>
                <button class="btn btn-dark">Control Bar</button>

                <img src="" alt="">
            </li>
            <li>
                <!-- Search bar -->
                <div class="search-area d-flex">
                    <textarea class="form-control search-bar" name="" id="" rows="1"></textarea>
                    <button class="btn btn-dark">Search</button>
                </div>
                <!-- logo -->
            </li>
            <li>
                <button class="btn btn-dark">OK</button>
            </li>
        </ul>
    </nav>
</template>

<script>
</script>

<style scoped>
.navbar {
    width: 100%;
    min-height: 40px;
}

.navbar-list {
    list-style: none;
}

.search-area {
    align-items: center;
    place-content: center;
    margin-block-start: auto;
}

.search-bar {
    resize: none;
    border-radius: 5px;
    border: 1px solid #babaca;
}
</style>