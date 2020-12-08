<template>
	<v-app class="pink lighten-4">
		<v-container>
			<v-row>
				<v-col cols="12" md="6"></v-col>
				<v-col cols="12" md="6">
					<v-row justify="center">
						<v-col cols="12" md="10">
							<v-card class="text-center my-5 py-5 px-5">
								<h1 class="blue--text">Forgot Password</h1>
								<v-form class="mx-5 my-5" ref="form">
									<v-text-field
										required
										label="Email"
										prepend-icon="mdi-mail"
										v-model="email"
										autofocus
										:rules="emailRules"
									></v-text-field>
									<v-btn color="blue" dark block @click="Submit">Get Token</v-btn>
								</v-form>
							</v-card>
						</v-col>
					</v-row>
				</v-col>
			</v-row>
		</v-container>
	</v-app>
</template>

<script>
	export default {
		data () {
			return {
				email: "",
				emailRules: [
					v => !!v || 'Please Enter Email',
					v => /.+@.+/.test(v) || 'E-mail must be valid',
				]
			}
		},

		methods: {
			Submit () {
				this.$refs.form.validate();

				// Would solve this later
			}
		}
	}
</script>