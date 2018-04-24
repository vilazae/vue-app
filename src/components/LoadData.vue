<template>
	<div>
		<h1>Data</h1>

		<ul>
			<li v-for="item in items">{{item}}</li>
		</ul>					
		
	</div>
</template>

<script>
import axios from 'axios';

export default {
	name: 'formulario',
	data:function () {
		return {
			items : [1,2],
			email : ""
		}
	},
	created: function() {
		console.log('created')
		const HTTP = axios.create({
			baseURL: `https://cloudpanel-api.1and1.com/v1/`,
			headers: {
				// 'X-API-TOKEN' : '34e461f34ecd343852b431bf06b2ee8b',
				'X-TOKEN' : '34e461f34ecd343852b431bf06b2ee8b',
				'Content-Type': 'application/json'
			}
		});
		HTTP.get( '/servers' )
		.then( function( response ) {
			console.log(response)

		}, function( error ) {
			console.log(error)
		});
		
		// 34e461f34ecd343852b431bf06b2ee8b
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