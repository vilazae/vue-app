<template>
	<div>
		<h1>Table</h1>
		<v-data-table
			:headers="headers"
			:items="items"
			hide-actions
			class="elevation-1"
		>
			<template slot="items" slot-scope="props">
				<td class="text-xs-right">{{ props.item.name }}</td>
				<td class="text-xs-right">{{ props.item.color }}</td>
				<td class="text-xs-right">{{ props.item.gender }}</td>
			</template>
		</v-data-table>
					
		
	</div>
</template>
<script>
export default {
	name: 'formulario',
	data:function () {
		return {
			items : [
				{
					name : 'Jhon',
					color : 'blue',
					gender : 'male'
				},
				{
					name : 'Peter',
					color : 'red',
					gender : 'male'
				},
				{
					name : 'Tomy',
					color : 'red',
					gender : 'male'
				},
				{
					name : 'Christine',
					color : 'blue',
					gender : 'female'
				}
			],
			headers : [
				{
				  text: 'Nombre',
				  value: 'name',
				  align: 'left',
				  sortable: true
				},
				{
				  text: 'Color',
				  value: 'color',
				  align: 'left',
				  sortable: true
				},
				{
				  text: 'Gender',
				  value: 'gender',
				  align: 'left',
				  sortable: true
				}
			],
			email : ""

		}
	},
	methods: {
		enviaFormulario : function () {
			console.log(this)
			// this.$validator.validateAll().then(
			// 	function( result ){
			// 		console.log(result)
			// 	}
			// )
			// this.listado.push( this.nombre );
			// this.nombre = "";
		}
	}
}
</script>