<template>
	<v-container fluid>
		<v-app-bar
			color="deep-purple accent-4"
			dark
		>
			<v-spacer />
			<v-btn
				outlined
				class="ml-3"
				>Главная</v-btn
			>
			<v-btn
				outlined
				class="ml-3"
				>Фото</v-btn
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

<style scoped></style>
