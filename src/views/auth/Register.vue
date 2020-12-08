<template>
	<v-app class="pink lighten-4">
		<v-container>
			<v-row>
				<v-col cols="12" md="6"></v-col>
				<v-col cols="12" md="6">
					<v-row justify="center">
						<v-col cols="12" md="10">
							<v-card class="text-center my-5 py-5 px-5">
								<h1 class="blue--text">Register</h1>
								<v-form class="mx-5 my-5" ref="form">
									<v-text-field
										required
										label="First Name"
										prepend-icon="mdi-account"
										:rules="nameRules"
										autofocus
										v-model="firstName"
									></v-text-field>
									<v-text-field
										required
										label="Last Name"
										prepend-icon="mdi-account"
										:rules="nameRules"
										v-model="lastName"
									></v-text-field>
									<v-text-field
										required
										label="Email"
										prepend-icon="mdi-mail"
										:rules="emailRules"
										v-model="email"
									></v-text-field>
									<v-text-field
										required
										label="Password"
										prepend-icon="mdi-lock"
										:append-icon="showP ? 'mdi-eye' : 'mdi-eye-off'"
										@click:append="showP = !showP"
										:type="showP ? 'text' : 'password'"
										:rules="passwordRules"
										v-model="password"
									></v-text-field>
									<v-text-field
										required
										label="Confirm Password"
										prepend-icon="mdi-lock"
										:append-icon="showCP ? 'mdi-eye' : 'mdi-eye-off'"
										@click:append="showCP = !showCP"
										:type="showCP ? 'text' : 'password'"
										:rules="passwordRules"
										v-model="confirmPassword"
									></v-text-field>
									<v-btn color="blue" dark block @click="Submit">Register</v-btn>
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
				showP: false,
				showCP: false,
				firstName: "",
				lastName: "",
				email: "",
				password: "",
				confirmPassword: "",
				nameRules: [
					v => !!v || 'Name Cannot Be Empty',
				],
				emailRules: [
					v => !!v || 'Please Enter Email',
					v => /.+@.+/.test(v) || 'E-mail must be valid',
				],
				passwordRules: [
					v => !!v || 'Please Provide Password',
					v => v.length >= 8 || 'Password Must Be At Least 8 Characters',
					v => v.length <= 20 || 'Password Must Be Less than 21 Characters',
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