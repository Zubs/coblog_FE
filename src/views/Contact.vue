<template>
	<v-app class="pink lighten-4">
		<h1>Contact</h1>
	</v-app>
</template>

<script>
	export default {
		data () {
			return {
				from: '',
				fromRules: [
					v => !!v || 'Please Enter Email',
					v => /.+@.+/.test(v) || 'Please Enter Valid Email',
				],
				subject: '',
				body: '',
				bodyRules: [
					v => !!v || 'Message Body Is Required',
				],
				name: '',
				status: false // This would be used to know when to pop up alert and redirect, maybe
			}
		},

		methods: {
			postContact () {

				// Get variables
				var formData = {
					from: this.from,
					subject: this.from,
					body: this.body,
					name: this.name,
				};

				// See data
				console.log(formData);

				// Make API call
				fetch('/api/contact', {
					method: 'post',
					body: JSON.stringify(formData),
					headers: {
						'content-type': 'application/json'
					}
				})
					.then(res => res.json())
					.then(res => {
						this.status = res ? true : false;
					})
					.catch(err => console.log(err))
			}
		}
	}
</script>