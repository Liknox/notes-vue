<template>
    <div class="wrappper">
        <div class="wrapper-content">
            <section>
                <div class="container">
                    <h1>{{ title }}</h1>

                    <message v-if="message" :message="message"/>
                    
                    <!-- new note -->
                    <div class="new-note">
                        <input v-model="note.title" type="text" />
                        <textarea v-model="note.descr"></textarea>
                        <button @click="addNote">New note</button>
                    </div>

                    <!-- note list -->
                    <div class="notes">
                        <div class="note" v-for="(note, index) in notes" :key="index">
                            <div class="note-header">
                                <p>{{ note.title }}</p>
                            </div>
                            <div class="note-body">
                                <p>{{ note.descr }}</p>
                                <span> {{ note.date }} </span>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </div>
</template>
<script>
import message from "@/components/message.vue"
export default {
	components: {
		message,
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
				this.message = "title can't be empty"
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
