<template>
	<nav>

		<!-- Navbar -->
		<v-toolbar flat app class="pink lighten-4">
			<v-app-bar-nav-icon @click.stop="drawer = !drawer" class="pink--text"></v-app-bar-nav-icon>
			<v-toolbar-title>
				<span class="font-weight-light pink--text">Co</span>
				<span class="text-uppercase blue--text text--lighten-3">Blog</span>
			</v-toolbar-title>
			<v-spacer></v-spacer>
			<v-btn color="pink" outlined class="mx-2" router to="login">
				<span>Login</span>
				<v-icon right>mdi-exit-to-app</v-icon>
			</v-btn>
			<v-btn color="pink" outlined class="mx-2" router to="register">
				<span>Register</span>
				<v-icon right>mdi-exit-to-app</v-icon>
			</v-btn>
		</v-toolbar>

		<!-- Drawer -->
		<v-navigation-drawer app class="pink lighten-4" v-model="drawer">
			<v-list>
				<v-list-item v-for="link in links" :key="link.route" router :to="link.route">
					<v-list-item-icon>
						<v-icon>mdi-{{ link.icon }}</v-icon>
					</v-list-item-icon>
					<v-list-item-content>
						<v-list-item-title v-text="link.text"></v-list-item-title>
					</v-list-item-content>
				</v-list-item>
			</v-list>
		</v-navigation-drawer>
	</nav>
</template>

<script>
	export default {
		data () {
			return {
				drawer: false,
				links: [
					{
						icon: 'dns',
						text: 'Home',
						route: '/'
					},
					{
						icon: 'folder',
						text: 'About',
						route: '/about'
					},
					{
						icon: 'account',
						text: 'Contact',
						route: '/contact'
					}
				]
			}
		}
	}
</script>