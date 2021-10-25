<template>
    <div class="container">
        <div class="columns">
            <div class="column">
                <h1 class="title">Lista de Produtos</h1>
            </div>
            <div class="column is-half"></div>
            <div class="column btn-column">
                <b-button 
                    label="Adicionar" 
                    type="is-info" 
                    icon-pack="fas"
                    icon-left="plus"
                    @click="addProduct"
                />
            </div>
        </div>
        <ProductTable :products="products" :editProduct="editProduct" />
        <b-modal
            v-model="isProductModalActive"
            has-modal-card
            trap-focus
            aria-role="dialog"
            aria-modal
        >
            <template #default="props">
                <ProductModal :product="selectedProduct" @close="props.close"/>
            </template>
        </b-modal>
    </div>
</template>

<script>
//import DeleteProductModal from '../components/DeleteProductModal.vue'
import ProductModal from '../components/ProductModal.vue'
import ProductTable from '../components/ProductTable.vue'

export default {
    components: {
        //DeleteProductModal,
        ProductModal,
        ProductTable
    },
    data() {
        return {
            products: [
                { 'id': 1, 'name': 'Samsung Galaxy S21', 'category': 'Celulares e Tablets', 'price': 3000.0, 'description': 'Blablabla' },
                { 'id': 2, 'name': 'Samsung Galaxy Z Flip 3', 'category': 'Celulares e Tablets', 'price': 4000.0, 'description': 'Blablabla' },
            ],
            selectedProduct: null,
            isProductModalActive: false,
            isDeleteProductModalActive: false
        }
    },
    methods: {
        addProduct() {
            this.selectedProduct = null;
            this.isProductModalActive = true;
        },
        editProduct(product) {
            this.selectedProduct = product;
            this.isProductModalActive = true;
        }
    }
}
</script>

<style scoped>
.container {
    height: 100%;
}

.columns {
    padding-top: 3.6rem;
}

.btn-column {
    display: flex;
    justify-content: end;
}
</style>
