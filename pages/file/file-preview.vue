<template>
	<view>
		<view class="">
			我测试一下
		</view>
		<web-view :src="allUrl"></web-view>
		<!-- <iframe :src="allUrl"></iframe> -->
	</view>
</template>

<script>
	import globalConfig from '@/config'
	export default {
		data() {
			return {
				viewerUrl: '/hybrid/html/web/viewer.html',
				// viewerUrl: globalConfig.baseUrl + '/pdf/web/viewer.html',
				allUrl: ''
			}
		},
		onReady() {
			// #ifdef APP-PLUS
			var currentWebview = this.$mp.page.$getAppWebview() //获取当前页面的webview对象
			setTimeout(function() {
				wv = currentWebview.children()[0]
				wv.setStyle({scalable:true})
			}, 1000); //如果是页面初始化调用时，需要延时一下
			// #endif
		},
		onLoad(options) {
			// let fileUrl = encodeURIComponent(
			// 	globalConfig.baseUrl + '/api/attachment?name=' + options.name + '&url=' + options.url)
			this.allUrl = this.viewerUrl + '?file=' + 'https://tems.minecraft.education.jdcloud.com/2019/08/10/Block%20coding%20docs/Unit%201/Lesson%201/Educator%20Guide_Unit1_Lesson1_Chinese%20Beta17.pdf'
		}
	}
</script>
