<template>
	<div class="wrappper">
		<div class="wrapper-content">
			<section>
				<div class="container">
					<h1>{{ title }}</h1>

					<message :message="message" v-if="message" />

					<newNote :note="note" @addNotee="addNote" />

					<notes :notes="notes" />
				</div>
			</section>
		</div>
	</div>
</template>
<script>
import newNote from "@/components/NewNote.vue/"
import message from "@/components/Message.vue/"
import notes from "@/components/Notes.vue/"
export default {
	components: {
		notes,
		message,
		newNote,
	},
	data() {
		return {
			title: "Notes App",
			message: false,
			note: {
				title: "",
				descr: "",
			},
			notes: [
				{
					title: "First Project",
					descr: "Description for first note",
					date: new Date(Date.now()).toLocaleString(),
				},
				{
					title: "Second Project",
					descr: "Description for Second note",
					date: new Date(Date.now()).toLocaleString(),
				},
				{
					title: "Third Project",
					descr: "Description for Third note",
					date: new Date(Date.now()).toLocaleString(),
				},
			],
		}
	},
	methods: {
		addNote() {
			// console.log(this.note)

			// for th

			let {title, descr} = this.note

			if (title === "") {
				this.message = "Title can't be empty"
				return false
			}
			this.notes.push({
				// title: this.note.title
				// descr: this.note.descr
				title,
				descr,
				date: new Date(Date.now()).toLocaleString(),
			})
			this.message = null
			this.note.title = ""
			this.note.descr = ""
		},
	},
}
</script>

<style></style>
