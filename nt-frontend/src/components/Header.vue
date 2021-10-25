<template>
    <b-navbar class="is-light">
        <template #brand>
            <b-navbar-item>
                <h1 class="title">
                    {{ navbarBrand }}
                </h1>
            </b-navbar-item>
        </template>
    </b-navbar>
</template>

<script>
export default {
    data() {
        return {
            navbarBrand: "Novos Teckers"
        }
    }
}
</script>

<style scoped>
nav {
    padding: .8rem .2rem;
}
</style>
