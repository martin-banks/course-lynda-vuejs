<template>
	<div class="product-list">
		<h2>{{title}}</h2>
		<ul>
			<product-list-item 
				@remove="remove(i)" 
				v-for="(product, i) in products" 
				:product="product" 
				:key="product.id"
			>
			<hr />
			</product-list-item>
		</ul>
	</div>
</template>


<script>
import ProductListItem from './ProductListItem.vue'

export default {
	name: 'product-list',
	components: {
		'product-list-item': ProductListItem,
	},
	props: ['title', 'products'],
	methods: {
		remove(i) {
			this.products.splice(i, 1)
		}
	},


}

</script>


<style scoped>
h2 {
  margin-bottom: 40px;
}

ul {
  list-style-type: none;
}

</style>