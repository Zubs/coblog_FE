<template>
  <v-app>
    <v-content>
      <Nav></Nav>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script>
	import Nav from '@/components/Nav.vue'

	export default {
		components: {
			Nav
		}
	}
</script>