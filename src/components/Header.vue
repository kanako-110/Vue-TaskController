<template>
	<header>
		<h1>{{ title }}</h1>
		<Button text="add Task" color="green" />
	</header>
</template>

<script>
import Button from './Button';

export default {
	name: 'Header',
	// props名: type
	props: {
		title: String,
	},
	components: {
		Button,
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
