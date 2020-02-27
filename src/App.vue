<template>
	<div id="app" class="container">
		<h1>Forma Padrão</h1>

		<PostsLista id="1" :posts="posts"></PostsLista>

		<hr />

		<h1>Slots com escopo</h1>

		<PostsLista :posts="posts">
			<template v-slot="{meupost}">
				// Atribuição via desestruturação
				<h2>{{meupost.titulo}}</h2>
				<p>{{meupost.conteudo}}</p>
				<small>{{meupost.rodape}}</small>
			</template>
		</PostsLista>
	</div>
</template>

<script>
import PostsLista from "./components/PostsLista";

export default {
	components: {
		PostsLista
	},
	data() {
		return {
			posts: [
				{
					id: 1,
					titulo: "Post Components",
					conteudo:
						"Components are reusable Vue instances with a name: in this case, <button-counter>. We can use this component as a custom element inside a root Vue instance created with new Vue:",
					autor: "Autor 1"
				},
				{
					id: 2,
					titulo: "Post Slots",
					conteudo:
						"Vue implementa uma API de distribuição de conteúdo que é modelada após o atual detalhamento da especificação dos componentes da Web, usando o elemento <slot> para servir como saída de distribuição de conteúdos.",
					autor: "Autor 2"
				}
			]
		};
	}
};
</script> 

<style scoped>
.container {
	width: 960px;
	margin: auto;
}
</style>

