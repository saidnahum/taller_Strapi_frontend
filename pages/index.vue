<template>
	<div>
		<h1 class="container mx-auto text-2xl font-bold">Welcome to my blog</h1>
		<div v-for="product in products" :key="product.id">
			<!-- <pre>{{ product.categories}}</pre> -->
			<h1><strong>Producto:</strong> {{ product.title }}</h1>
			<div v-for="cat in product.categories" :key="cat.id">
				<p class="ml-5"><strong>Categoría: </strong>{{cat.name}}</p>
			</div>
		</div>

		<div v-for="post in posts" :key="post.id">
			<!-- <pre>{{ product.categories}}</pre> -->
			<h1><strong>Post Title:</strong> {{ post.title }}</h1>
			<div>
				<p><strong>Post URL:</strong> {{ post.video['title'] }}</p>
			</div>
			
		</div>
		
	</div>
</template>

<script>
export default {
	data() {
		return {
			products: [],
			posts: []
		}
	},
	mounted(){
		this.getPoducts()
		this.getPosts()
	},
	methods: {
		async getPoducts(){
			const res = await this.$axios.get('http://localhost:1337/products');
			console.log(res.data);
			this.products = res.data;
		},
		async getPosts(){
			const res = await this.$axios.get('http://localhost:1337/posts');
			console.log(res.data);
			this.posts = res.data;
		}
	}
}
</script>
