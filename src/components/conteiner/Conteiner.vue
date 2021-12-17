<template>
    <div>
        <p> 
        <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapseConteiner" aria-expanded="false" aria-controls="collapseConteiner">
            Contêiners
        </button>
        </p>
        <div class="collapse" id="collapseConteiner">
            <h2>Listagem de conteiner</h2>
            <table class="table strip">
                <thead>
                    <tr>
                        <th>Identificacao</th>
                        <th>Cliente</th>
                        <th>Tipo</th>
                        <th>Status</th>
                        <th>Categoria</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="cont,index in conteiners" :key="index">
                        <td>{{ cont.identificacao }}</td>
                        <td>{{ cont.cliente.nome}}</td>
                        <td>{{ cont.tipo}}</td>
                        <td>{{ cont.status}}</td>
                        <td>{{ cont.categoria}}</td>
                    </tr>
                </tbody>
            </table>
        </div>    
    </div>
</template>

<script>
    export default {
        props:{
            conteiners:{
                required: true
            }
        }
    }
</script>