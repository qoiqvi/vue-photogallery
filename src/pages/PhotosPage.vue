<template>
	<v-container>
		<PhotoForm @addPhoto="addPhoto" />
		<v-row>
			<PhotoItem
				v-for="photo in photos"
				:key="photo.id"
				v-bind:photo="photo"
				@openPhoto="openPhoto"
			/>
		</v-row>
		<PhotoDialog
			v-bind:photo="currentPhoto"
			v-model="dialogVisible"
		/>
	</v-container>
</template>

<script>
import PhotoItem from "@/components/photo/PhotoItem"
import PhotoForm from "@/components/photo/PhotoForm"
import PhotoDialog from "@/components/photo/PhotoDialog"
export default {
	name: "PhotosPage",
	components: {
		PhotoItem,
		PhotoForm,
		PhotoDialog,
	},
	mounted() {
		this.fetchPhotos()
	},
	data: () => ({
		photos: [],
		currentPhoto: {},
		dialogVisible: false,
	}),
	methods: {
		fetchPhotos() {
			this.axios
				.get("https://jsonplaceholder.typicode.com/photos?_limit=10")
				.then((res) => (this.photos = res.data))
		},
		addPhoto(photo) {
			this.photos.push(photo)
		},
		openPhoto(photo) {
			console.log(photo)
			this.currentPhoto = photo
			this.dialogVisible = true
		},
	},
}
</script>
<style></style>
