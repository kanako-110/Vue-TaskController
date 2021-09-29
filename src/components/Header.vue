<template>
	<header>
		<h1>{{ title }}</h1>
		<!-- : v-bind -->
		<Button
			v-show="homePage"
			@btn-click="$emit('toggle-add-task')"
			:text="showAddTask ? 'Close' : 'Add Task'"
			:color="showAddTask ? 'red' : 'Green'"
		/>
	</header>
</template>

<script>
import Button from './Button';

export default {
	name: 'Header',
	// props名: type
	props: {
		title: String,
		showAddTask: Boolean,
	},
	components: {
		Button,
	},
	computed: {
		homePage() {
			if (this.$route.path === '/') {
				return true;
			} else {
				return false;
			}
		},
	},
};
</script>

//scope: このコンポーネントの身に適応されるようになる
<style scoped>
header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-block-start: 20px;
}
</style>
