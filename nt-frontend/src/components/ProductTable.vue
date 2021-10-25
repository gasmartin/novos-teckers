<template>
    <div class="table-wrapper">
        <b-table :data="products" striped hoverable>
            <b-table-column field="id" label="ID" width="80" numeric centered v-slot="props">
                {{ props.row.id }}
            </b-table-column>

            <b-table-column field="name" label="Nome" width="260" centered v-slot="props">
                {{ props.row.name }}
            </b-table-column>

            <b-table-column field="category" label="Categoria" width="260" centered v-slot="props">
                {{ props.row.category }}
            </b-table-column>

            <b-table-column field="price" label="Preço" width="200" numeric centered v-slot="props">
                R$ {{ props.row.price.toFixed(2) }}
            </b-table-column>

            <b-table-column field="description" label="Descrição" centered v-slot="props">
                {{ props.row.description }}
            </b-table-column>

            <b-table-column field="actions" label="Actions" width="115" centered v-slot="props">
                <b-button
                    type="is-text"
                    icon-pack="fas"
                    icon-right="pen"
                    @click="editProduct(props.row)"
                />
                <b-button 
                    type="is-text"
                    icon-pack="fas"
                    icon-right="trash"
                />
            </b-table-column>

            <template #empty>
                <div class="has-text-centered">Não existem produtos...</div>
            </template>
        </b-table>
    </div>
</template>

<script>
export default {
    props: {
        products: {
            type: Array
        },
        editProduct: {
            type: Function
        }
    }
}
</script>

<style scoped>
.table-wrapper {
    padding: 1.4rem 0;
}
</style>
