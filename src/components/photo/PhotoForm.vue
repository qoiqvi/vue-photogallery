<template>
	<v-container>
		<v-row class="d-flex">
			<v-text-field v-model="title" />
			<v-file-input v-model="image" />
			<v-btn @click="addPhoto">Добавить</v-btn>
		</v-row>
	</v-container>
</template>
<script>
export default {
	name: "PhotoForm",
	data: () => ({
		title: "",
		image: null,
	}),
	methods: {
		addPhoto() {
			const reader = new FileReader()
			reader.onload = () => {
				let photo = {
					id: Date.now(),
					title: this.title,
					url: reader.result,
				}
				this.$emit("addPhoto", photo)
			}
			reader.readAsDataURL(this.image)
		},
	},
}
</script>
<style></style>
