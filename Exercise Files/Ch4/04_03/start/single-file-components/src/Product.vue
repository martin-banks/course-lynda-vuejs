<template>
	<div>
		<router-link to="/products" >Back to products</router-link>
		<img :src="info.image" />
		<h2>
			<strong>{{ info.name }}</strong>
		</h2>
		<p>{{ info.description }}</p>
		<p>${{ info.price }}</p>
		<button>Add to cart</button>
	</div>
</template>


<script scoped>
export default {
	name: 'product',
	data() {
		return {
			info: {}
		}
	},
	created() {
		$.getJSON(`https://hplussport.com/api/products/id/${this.$route.params.id}`)
			.done(data => {
				this.info = data[0]
				console.log(data[0])
			})

	}
}
</script>


<style scoped>
img {
  float: left;
  width: 300px;
}

li {
  margin-bottom: 40px;
  clear: both;
}
img.small {
  width: 100px;
}

</style>