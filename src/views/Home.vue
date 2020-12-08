<template>
	<v-app class="pink lighten-4">
		<h1>Home</h1>
	</v-app>
</template>

<script>
	export default {
		data () {
			return {
				posts: []
			}
		},

		methods: {
			getPosts () {
				fetch('/api/posts')
					.then(res => res.json())
					.then(res => {
						this.posts = res.data;
					})
					.catch(err => console.log(err))
			}
		},

		created () {
			this.getPosts();
		}
	}
</script>