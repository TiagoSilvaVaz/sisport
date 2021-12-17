<template>
    <div>
        <p> 
        <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapseMovimentacaoForm" aria-expanded="false" aria-controls="collapseMovimentacaoForm">
            Cadastrar Movimentação
        </button>
        </p>
        <div class="collapse" id="collapseMovimentacaoForm">
            <h1>Formulário Movimentação</h1>
            <div class="mb-3">
                <label for="input-documento" class="form-label">Conteiner</label>
                <select class="form-control" v-model="movimentacao.conteiner">
                    <option :value="cont" v-for="cont, index in conteiners" :key="index" >{{cont.identificacao}}</option>
                </select>
            </div>
            <div class="mb-3">
                <label for="input-documento" class="form-label">Tipo de Movimentação</label>
                <select v-model="movimentacao.tipo" class="form-control">
                    <option value="embarque">Embarque</option>
                    <option value="descarga">Descarga</option>
                    <option value="gate in">Gate in</option>
                    <option value="gate out">Gate out</option>
                    <option value="reposicionamento">Reposicionamento</option>
                    <option value="pesagem">Pesagem</option>
                    <option value="scanner">Scanner</option>
                </select>
            </div>
            <div>
                <p>Assinale horário e data de inicio:</p>
                <input v-model="movimentacao.data_inicio" type="date">
                <input v-model="movimentacao.hora_inicio" type="time">
                <p>Assinale horário e data de fim:</p>
                <input v-model="movimentacao.data_fim" type="date">
                <input v-model="movimentacao.hora_fim" type="time">
            </div>
                        
            <button @click="salvar" type="button" class="btn btn-success">Salvar</button>
        </div>    
    </div>
    
</template>

<script>
    export default {
        props:{
            conteiners:{
                required: true
            }
        },
        data: () => {
            return {
                movimentacao:{
                    conteiner:null,
                    tipo:''
                }
            }   
        },
        methods:{
            salvar(){
                let movimentacao = Object.assign({}, this.movimentacao)
                console.log(movimentacao)
                this.$emit('salvar', movimentacao)
            }
        }
    }
</script>