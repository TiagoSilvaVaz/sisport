<template>
	<div class="container">
		<Cliente :clientes="clientes" />
		<ClienteForm @salvar="aoSalvarUmCliente" />
		<Conteiner :conteiners="conteiners"/>
		<ConteinerForm :clientes="clientes" @salvar="aoSalvarUmConteiner" />
		<Movimentacao :movimentacoes="movimentacoes"/>
		<MovimentacaoForm :conteiners="conteiners" @salvar="aoSalvarUmaMovimentacao" />
	</div>
</template>

<script>
import Cliente from '@/components/cliente/Cliente'
import ClienteForm from '@/components/cliente/ClienteForm'
import Conteiner from '@/components/conteiner/Conteiner'
import ConteinerForm from '@/components/conteiner/ConteinerForm'
import Movimentacao from '@/components/movimentacao/Movimentacao'
import MovimentacaoForm from '@/components/movimentacao/MovimentacaoForm'

export default {
	name: 'App',
	components:{
		ClienteForm, Cliente, Conteiner, ConteinerForm, Movimentacao, MovimentacaoForm
	},
	data:()=>({
		clientes:[{nome:"Marcos", documento:"123.456.789-47"},{ "nome": "Lucas", "documento": "123.456.789-48" }],
		conteiners:[{ "identificacao": "12345MNHDFGHS", "cliente": { "nome": "Lucas", "documento": "12345678948" }, "tipo": "40", "status": "cheio", "categoria": "importacao" }],
		movimentacoes:[]
	}),
	mounted(){

	},
	methods:{
		aoSalvarUmCliente(novoCliente){
			this.clientes.push(novoCliente)
		},
		aoSalvarUmConteiner(novoConteiner){
			this.conteiners.push(novoConteiner)
		},
		aoSalvarUmaMovimentacao(novoMovimentacao){
			this.movimentacoes.push(novoMovimentacao)
		}
	}
}
</script>