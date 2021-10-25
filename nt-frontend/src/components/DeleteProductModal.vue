<template>
    <div class="card" style="width: 50vw">
        <header class="card-header">
            <p class="card-header-title is-size-4">
                Apagar?
            </p>
        </header>
        <div class="card-content py-5">
            Você tem certeza que deseja apagar este produto?
        </div>
        <footer class="card-footer is-justify-content-flex-end py-3">
            <b-button 
                label="Cancelar"
                @click="$emit('close')"
            />
            <b-button 
                label="Apagar"
                type="is-danger"
                class="mx-4"
                @click="deleteProduct(productId)"
            />
        </footer>
    </div>
</template>

<script>
export default {
    params: {
        productId: {
            type: Number
        }
    },
    methods: {
        deleteProduct(productId) {
            console.log(productId);
        }
    }
}
</script>