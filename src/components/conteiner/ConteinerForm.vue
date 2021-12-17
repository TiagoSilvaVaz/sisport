<template>
    <div>
        <p> 
        <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapseConteinerForm" aria-expanded="false" aria-controls="collapseConteinerForm">
            Cadastrar Contêiner
        </button>
        </p>
        <div class="collapse" id="collapseConteinerForm">
            
            <h1>Formulário conteiner</h1>
            <div class="mb-3">
                <label for="input-nome" class="form-label">Identificação</label>
                <input type="text" class="form-control" id="input-nome" placeholder="Identificacao" v-model="conteiner.identificacao"/>
            </div>

            <div class="mb-3">
                <label for="input-documento" class="form-label">Cliente</label>
                <select class="form-control" v-model="conteiner.cliente">
                    <option :value="cli" v-for="cli, index in clientes" :key="index" >{{cli.nome}}</option>
                </select>
            </div>

            <div class="mb-3">
                <label for="input-documento" class="form-label">Tipo</label>
                <select class="form-control" v-model="conteiner.tipo">
                    <option value="20">20</option>
                    <option value="40">40</option>
                </select>
            </div>

            <div class="mb-3">
                <label for="input-documento" class="form-label">Status</label>
                <select class="form-control" v-model="conteiner.status">
                    <option value="cheio">Cheio</option>
                    <option value="vazio">Vazio</option>
                </select>
            </div>

            <div class="mb-3">
                <label for="input-documento" class="form-label">Categoria</label>
                <select class="form-control" v-model="conteiner.categoria">
                    <option value="importacao">Importação</option>
                    <option value="exportacao">Exportação</option>
                </select>
            </div>
                        
            <button @click="salvar" type="button" class="btn btn-success">Salvar</button>
        </div>    
    </div>
    
</template>

<script>
    export default {
        props:{
            clientes:{
                required: true
            }
        },
        data: () => {
            return {
                conteiner:{
                    identificacao:'',
                    cliente:null,
                    tipo:'',
                    status:'',
                    categoria:''
                }
            }   
        },
        methods:{
            salvar(){
                let conteiner = Object.assign({}, this.conteiner)
                console.log(conteiner)
                this.$emit('salvar', conteiner)
            }
        }
    }
</script>