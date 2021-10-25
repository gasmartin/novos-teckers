<template>
    <div class="card" style="width: 50vw">
        <header class="card-header">
            <p class="card-header-title is-size-4">
                {{ modalTitle }}
            </p>
        </header>
        <div class="card-content py-5">
            <b-field label="Nome">
                <b-input
                    v-model="productData.name"
                    required
                ></b-input>
            </b-field>
            <b-field 
                label="Categoria"
            >
                <b-select 
                    v-model="productData.category" 
                    required
                >
                    <option 
                        v-for="(category, index) in categories"
                        :key="index"
                        :value="category"
                    >
                        {{ category }}
                    </option>
                </b-select>
            </b-field>
            <b-field label="Preço">
                <b-input
                    v-model="productData.price"
                    type="number"
                    step="0.01"
                    required
                ></b-input>
            </b-field>
            <b-field label="Descrição">
                <b-input
                    v-model="productData.description"
                ></b-input>
            </b-field>
        </div>
        <footer class="card-footer is-justify-content-flex-end py-3">
            <b-button 
                label="Cancelar"
                @click="$emit('close')"
            />
            <b-button 
                :label="buttonContent"
                type="is-info"
                class="mx-4"
                @click="submitData"
            />
        </footer>
    </div>
</template>

<script>
export default {
    props: {
        product: {
            type: Object
        }
    },
    created() {
        if(this.product) {
            this.productData = this.product;
        }
    },
    data() {
        return {
            productData: {
                name: "",
                category: "",
                price: 0.0,
                description: ""
            },
            categories: [
                "Celulares e Tablets", "Eletrodomésticos", "Periféricos e Acessórios", "Televisores"
            ]
        };
    },
    computed: {
        modalTitle() {
            return this.product ? 'Editar Produto' : 'Adicionar Novo Produto';
        },
        buttonContent() {
            return this.product ? 'Salvar' : 'Adicionar';
        }
    },
    methods: {
        submitData() {
            if(this.buttonContent == 'Adicionar') {
                console.log('Adicionar');
            }
            else {
                console.log('Salvar');
            }
            this.$emit('close');
        }
    }
}
</script>