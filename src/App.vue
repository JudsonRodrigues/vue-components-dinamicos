<template>
	<div id="app" class="container">
		<h1>Components dinâmicos</h1>

		<button @click="componentSelecionado = 'Home'">Home</button>
		<button @click="componentSelecionado = 'PostsLista'">Posts</button>
		<button @click="componentSelecionado = 'Sobre'">Sobre</button>

		<p>{{componentSelecionado}}</p>

		<component :is="componentSelecionado" v-bind="propsAtuais"></component>
	</div>
</template>

<script>
import Home from "./components/Home";
import PostsLista from "./components/PostsLista";
import Sobre from "./components/Sobre";

export default {
	components: {
		// eslint-disable-next-line vue/no-unused-components
		PostsLista,
		// eslint-disable-next-line vue/no-unused-components
		Home,
		// eslint-disable-next-line vue/no-unused-components
		Sobre
	},
	data() {
		return {
			componentSelecionado: "Home",
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
	},
	computed: {
		propsAtuais() {
			return this.componentSelecionado === "PostsLista"
				? { posts: this.posts }
				: {};
		}
	}
};
</script> 

<style scoped>
.container {
	width: 960px;
	margin: auto;
}
</style>

