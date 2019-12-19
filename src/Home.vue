<template>
<div id="app">
	<layout>
		<template #header="header">
			<h1>{{header.title}}</h1>
		</template>
		<template #sidebar="sidebar">
			<ul class="menu">
				<li v-for="sidebar of sidebars" :key="sidebar.menu">
					<!-- <a :href="sidebar.link">{{sidebar.menu}}</a> -->
					<router-link :to="sidebar.link">{{sidebar.menu}}</router-link>
				</li>
			</ul>
		</template>
		<template #content="content">
			<router-view/>
		</template>
		<template #footer="footer">
			<h3>{{footer.foot}}</h3>
		</template>
	</layout>
</div>
</template>
<script>
import Layout from "@/components/Layout.vue"
export default{
	components : {Layout},
	data(){
		return{
			sidebars:[
				{menu:"장바구니",link:"/cart"},
				{menu:"계산기",link:"/calculator"},
				{menu:"자연수의 합",link:"/seqsum"},
				{menu:"은행",link:"/bank"},
				{menu:"할일",link:"/todo"}
			]
		}
	}
}
</script>
<style scoped>
ul.menu {
    position:relative;
    padding: 5px 5px 5px 5px;
    list-style: none;
    font-style: italic;
}
ul.menu a {
    text-decoration:none;
}
</style>