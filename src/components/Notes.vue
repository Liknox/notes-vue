<template>
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
</template>

<script>
export default {
	props: {
		notes: {
			type: Array,
			required: true,
		},
	},
}
</script>

<style lang="scss">
.notes {
	display: flex;
	align-items: center;
	justify-content: space-between;
	flex-wrap: wrap;
	padding: 40px 0;
}
.note {
	width: 48%;
	padding: 18px 20px;
	margin-bottom: 20px;
	background-color: #ffffff;
}
.note-header {
	p {
		color: #402caf;
		font-size: 22px;
	}
}
.note-body {
	p {
		margin: 20px 0;
	}
	span {
		font-size: 14px;
		color: #999999;
	}
}
</style>
