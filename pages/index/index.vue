<template>
	<view class="content"><web-view :src="url"></web-view></view>
</template>

<script>
export default {
	data() {
		return {
			// pdf.js的viewer.htm所在路径
			// 注意：静态的html文件需要放在根路径下的 hybrid/html 文件夹中
			viewerUrl: '/hybrid/html/web/viewer.html',
			// 要访问的pdf的路径
			fileUrl: './test.pdf',
			// 最终显示在web-view中的路径
			url: ''
		};
	},
	onLoad() {
		// h5 和 安卓 都使用，使用h5访问的时候记得跨域
		this.url = `${this.viewerUrl}?file=${encodeURIComponent(this.fileUrl)}`;
		// 在安卓和ios手机上，取消下面的注释即可
		// 判断是手机系统：安卓，使用pdf.js
		// if(plus.os.name === 'Android') {
		// 	this.url = `${this.viewerUrl}?file=${encodeURIComponent(this.fileUrl)}`;
		// }
		// // ios，直接访问pdf所在路径
		// else {
		// 	this.url = encodeURIComponent(this.fileUrl);
		// }
	},
	methods: {}
};
</script>

<style>
</style>
