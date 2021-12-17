<template>
    <div>
        <p> 
        <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapseCliente" aria-expanded="false" aria-controls="collapseCliente">
            Clientes
        </button>
        </p>
        <div class="collapse" id="collapseCliente">
            <div class="card card-body">
                <h2>Listagem de Clientes</h2>
                <table class="table strip">
                    <thead>
                        <tr>
                            <th>Nome</th>
                            <th>Documento</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="cli,index in clientes" :key="index">
                            <td>{{cli.nome}}</td>
                            <td>{{cli.documento}}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props:{
            clientes:{
                required: true
            }
        }
    }
</script>