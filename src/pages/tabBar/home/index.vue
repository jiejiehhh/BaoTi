<template>

	<view class="head">
		<view class="head-nav" v-for="nav in navData" :key="index">
			<image class="nav-icon" :src="nav.icon" alt="" />
			<text class="nav-title">{{nav.title}}</text>
		</view>
	</view>
	<view class="content">
		<view class="notice">
			<image class="icon5" src="/static/home/icon5.png" mode=""></image>
			<text class="notice-con">关于XXX平台的使用介绍，文案向左滑动循环展播</text>
		</view>
		<view class="video">
			<view class="video-top">
				<video class="video-w" src=""></video>
			<text class="describe">首页视频文案默认展示三行，可考虑类似音首页视频文案默认展示三行，可考虑类似音首页视频文案默认展示三行，可考虑类似音</text>
			</view>
			
			<view class="conllect">
				<view class="con-left">
					<text class="con-text">职场吗哪  2022/11/21</text>					
				</view>
				<div class="conRightBox">
					<view class="con-right">
					<image  src="/src/static/home/star.png" mode=""></image>
					<image style="display: none;" src="/src/static/home/star2.png" mode=""></image>				
				</view>
				<view class="con-right back">
					<image  src="/src/static/home/star.png" mode=""></image>
					<image style="display: none;" src="/src/static/home/star2.png" mode=""></image>				
				</view>
				</div>
				
			</view>
		</view>
	</view>
</template>

<script setup lang="ts">
	import {
		computed,
		ref
	} from 'vue'
	import {
		useAppStore
	} from '@/store/modules/app';
	import {
		storeToRefs
	} from 'pinia';
	interface ColumnProps {
		id: number;
		title: string;
		icon: string;
	}
	const navData: ColumnProps[] = [{
			id: 1,
			title: "主日讲道",
			icon: "/static/home/icon1.png"
		},
		{
			id: 2,
			title: "职场吗哪",
			icon: "/static/home/icon1.png"
		},
		{
			id: 3,
			title: "每日灵修",
			icon: "/static/home/icon1.png"
		},
		{
			id: 4,
			title: "我的建议",
			icon: "/static/home/icon1.png"
		},
	]
</script>

<style>
	.content {
		padding: 0 18px;
	}

	.head {
		display: flex;
		align-items: center;
		justify-content: space-around;
		padding: 30px 0;
	}

	.head-nav {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;

	}

	.nav-icon {
		height: 40px;
		width: 40px;
		margin-bottom: 8px;
	}

	.nav-title {
		font-size: 12px;
		color: #6C7073;
	}

	.notice {
		display: flex;
		align-items: center;
		background: linear-gradient(90deg, rgba(0, 123, 199, 0.04) 0%, rgba(255, 255, 255, 0.24) 100%);
		box-shadow: 0px 1px 4px 0px rgba(0, 123, 199, 0.12);
		border-radius: 18px;
		background-image: url('/src/static/home/arrow-right.png') no-repeat center right;
		margin-bottom: 20px;
	}
	.notice::-webkit-scrollbar{
		display: none;
	}
	.icon5 {
		width: 36px;
		height: 36px;
		margin-right: 7px;

	}

	.notice-con {
		overflow-x: auto;
		white-space: nowrap;
		width: 80%;
		box-sizing: border-box;
		overflow-x: scroll;
		color: rgba(0,123,199,0.64);
		font-size: 12px;
	}
	.video{
		background: rgba(0,123,199,0.12);
		box-shadow: 0px 2px 8px 0px rgba(0,123,199,0.12);
		border-radius: 16px;
		
	}
	.video-top{
		padding: 20px 16px;
	}
	.video-w{
		width: 100%;
		height: 150px;
		background: rgba(0,0,0,0.24);
		border-radius: 16px;
		
	}
	.describe{
		font-size: 14px;
		font-family: PingFangSC-Regular, PingFang SC;
		font-weight: 400;
		color: #6C7073;
		line-height: 22px;
		padding: 20px 14px;
		text-align: justify;
		      overflow: hidden;
		      text-overflow: ellipsis;
		      width: 100%;
		      display: -webkit-box;
		      -webkit-box-orient: vertical;
		      -webkit-line-clamp: 3;
		      word-break: break-all;

	}
	.conllect{
		display: flex;
		justify-content: space-between;
		align-items: center;
		height: 48px;
		background: rgba(0,123,199,0.08);
		border-radius: 16px;
		
	}
	.con-left{
		font-size: 12px;
		color: #007BC7;
		padding-left: 20px;
	}
	.conRightBox{
		display: flex;
		
	}
	.con-right{
		width: 48px;
		height: 48px;
		background: linear-gradient(155deg, rgba(0,149,213,0.16) 0%, rgba(0,123,199,0.48) 100%);
		border-radius: 16px 0px 0px 0px;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.back{
		background: linear-gradient(138deg, #0095D5 0%, #007BC7 100%);;
	}
	.con-right image{
		width: 20px;
		height: 20px;
	}
</style>
