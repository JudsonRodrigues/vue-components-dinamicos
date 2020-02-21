<template>
	<div id="app">
		<h1>Vue JS</h1>

		<Post titulo="Titulo"></Post>
		<Post titulo="Passando dados via props"></Post>

		<h2>Componentes no vue</h2>
		<p>A component can have as many props as you’d like and by default, any value can be passed to any prop. In the template above, you’ll see that we can access this value on the component instance, just like with data.</p>
	</div>
</template>

<script>
import Post from "./components/Post";

export default {
	components: {
		Post
	}
};
</script>