<template>
    <div>
        <p> 
            <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapseClienteForm" aria-expanded="false" aria-controls="collapseClienteForm">
                Cadastrar Cliente
            </button>
        </p>
        <div class="collapse" id="collapseClienteForm">
            <h1>Formulário Cliente</h1>
            <div class="mb-3">
                <label for="input-nome" class="form-label">Nome</label>
                <input type="text" class="form-control" id="input-nome" placeholder="Nome" v-model="cliente.nome"/>
            </div>
            <div class="mb-3">
                <label for="input-documento" class="form-label">Documento</label>
                <input type="text" class="form-control" id="input-documento" v-mask="'###.###.###-##'" placeholder="CPF" v-model="cliente.documento"/>
            </div>
            <button @click="salvar" type="button" class="btn btn-success">Salvar</button>
        </div>
    </div>
</template>

<script>
    export default {
        data: () => {
            return {
                cliente:{
                    nome:'',
                    documento:''
                }
            }   
        },
        mounted(){ //componente montado na página

        },
        methods:{
            salvar(){
                let cliente = Object.assign({}, this.cliente)
                this.$emit('salvar', cliente)
                this.cliente.nome =  "";
                this.cliente.documento = "";
            }
        }
    }
</script>