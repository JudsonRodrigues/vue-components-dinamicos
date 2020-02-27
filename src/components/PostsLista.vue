<template>
	<div>
		<h2>Lista de posts</h2>

		<PostsListaIten v-for="post in posts" :key="post.id" :post="post">
			<slot :meupost="post"></slot>
		</PostsListaIten>
	</div>
</template>
<script>
import PostsListaIten from "./PostListaIten.vue";

export default {
	components: { PostsListaIten },
	props: {
		posts: {
			type: Array,
			required: true
		}
	}
};
</script>