<template> <!-- Componente root da aplicação -->

	<div> <!-- Templates do vue só podem ter um elemento root por isso, é normalmente visto divs logo após a tag template -->
		<HelloWorld/>
		<p>{{ testando }}</p>
	</div>
	
</template>

<script>
import HelloWorld from './components/Helloword/HelloWorld.vue';

export default {
	name: 'App',
	
	components:{
		HelloWorld,
	},

	data() {
		return {
			testando: 'Teste de componente (app também é um componente) ',
		}
	}
}
</script>