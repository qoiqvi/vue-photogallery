<template>
	<v-container fluid>
		<v-app-bar
			color="deep-purple accent-4"
			dark
		>
			<v-spacer />

			<router-link to="/">
				<v-btn
					outlined
					class="ml-3 linkBtn"
					>Главная</v-btn
				></router-link
			>
			<router-link to="/photos">
				<v-btn
					outlined
					class="ml-3 linkBtn"
					>Фото
				</v-btn></router-link
			>
		</v-app-bar>
	</v-container>
</template>

<script>
export default {
	// eslint-disable-next-line vue/multi-word-component-names
	name: "Navbar",
}
</script>

<style scoped>
.linkBtn {
	text-decoration: none;
}
</style>
