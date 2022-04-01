<template>
    <header class="bg-dark d-flex align-items-center">
        <div class="container">
            <div class="row text-white">
                <div class="col-12">
                    <nav class="navbar d-flex justify-content-end">
                        <form class="d-flex">
                        <input class="form-control me-2 bg-dark border" type="search" placeholder="Search" aria-label="Search">
                        <button class="btn btn-outline-danger" type="submit">Search</button>
                        </form>
                    </nav>
                </div>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: "IndexHeader"
}
</script>

<style lang="scss" scoped>
    header{
        height: 15vh;
    }
</style>