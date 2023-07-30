<template>
	<v-dialog
		v-model="dialogVisible"
		persistent
		max-width="600"
	>
		<v-card>
			<v-card-title class="text-h5"> {{ photo.title }}</v-card-title>
			<v-card-text>
				<v-img v-bind:src="photo.url" />
			</v-card-text>
		</v-card>
	</v-dialog>
</template>

<script>
export default {
	name: "PhotoDialog",
	props: {
		photo: {
			type: Object,
			required: true,
		},
		value: {
			type: Boolean,
		},
	},
	created() {
		this.dialogVisible = this.value
	},
	data: () => ({
		dialogVisible: false,
	}),
	watch: {
		value(newValue) {
			this.dialogVisible = newValue
		},
		dialogVisible(newValue) {
			this.$emit("input", newValue)
		},
	},
}
</script>
<style lang=""></style>
