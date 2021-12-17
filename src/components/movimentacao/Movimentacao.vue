<template>
    <div>
        <p> 
        <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapseMovimentacao" aria-expanded="false" aria-controls="collapseMovimentacao">
            Movimentação
        </button>
        </p>
        <div class="collapse" id="collapseMovimentacao">
            <h2>Listagem de Movimentação</h2>
            <table class="table strip">
                <thead>
                    <tr>
                        <th>Conteiner</th>
                        <th>Cliente</th>
                        <th>Tipo</th>
                        <th>Data inicio</th>
                        <th>Data fim</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="mov,index in movimentacoes" :key="index">
                        <td>{{ mov.conteiner.identificacao}}</td>
                        <td>{{ mov.conteiner.cliente.nome}}</td>
                        <td>{{ mov.tipo}}</td>
                        <td>{{ mov.data_inicio}} {{mov.hora_inicio}}</td>
                        <td>{{ mov.data_fim}} {{mov.hora_fim}}</td>
                    </tr>
                </tbody>
            </table>
        </div>    
    </div>
</template>

<script>
    export default {
        props:{
            movimentacoes:{
                required: true
            }
        }
    }
</script>