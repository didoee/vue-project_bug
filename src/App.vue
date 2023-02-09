<script setup lang="ts">
import { useDark, useToggle } from '@vueuse/core';

const isDark = useDark({
	onChanged(value) {
		console.log('dark mode changed', value);
	},
});
// const toggleDark = useToggle(isDark);
const toggleDark = () => {
	isDark.value = !isDark.value;
};
</script>

<template>
	<div>
		<el-button @click="toggleDark">切换主题</el-button>
		<span> 当前状态是: {{ isDark }} </span>
		<div>
			<el-button>Default</el-button>
			<el-button type="primary">Primary</el-button>
			<el-button type="success">Success</el-button>
			<el-button type="info">Info</el-button>
			<el-button type="warning">Warning</el-button>
			<el-button type="danger">Danger</el-button>
		</div>
	</div>
</template>
