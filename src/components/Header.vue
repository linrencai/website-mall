<template>
	<div>
		<ul>
			<li
				v-for="(item, index) in tabList"
				@click="changeTabs(index)"
				:key="index"
				:class="{active:index == activeIndex}"
			>
				{{ item.name }}
			</li>
		</ul>
	</div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
type tabItemType = {
	index: number;
	name: string;
};
const tabList: tabItemType[] = [
	{
		index: 0,
		name: 'tab1',
	},
	{
		index: 1,
		name: 'tab2',
	},
	{
		index: 2,
		name: 'tab3',
	},
	{
		index: 3,
		name: 'tab4',
	},
];
export default defineComponent({
	name: 'Header',
	setup() {
		const activeIndex = ref<number>(0);
		function changeTabs(i: number) {
			activeIndex.value = i;
		}
		return { tabList, changeTabs,activeIndex };
	},
});
</script>
<style lang="less" scoped>
.active {
	color: red;
}
</style>
