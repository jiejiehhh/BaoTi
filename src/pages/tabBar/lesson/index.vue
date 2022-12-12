<template>
	<view class="lesson_bg">
		<image src="" mode=""></image>
	</view>
	<view class="head">
		<view class="head-nav" v-for="nav in navData" :key="index">
			<image class="nav-icon" :src="nav.icon" alt="" />
			<text class="nav-title">{{nav.title}}</text>
		</view>
	</view>
	<view class="mainbox">
		<view class="lesson-box">
			<view class="mine-lesson">
				<view class="mine-title">
					我的课程
				</view>
				<view class="more-title">
					更多
				</view>
			</view>
			<view class="content-box" v-for="mine in mineData" :key="index">
				<image class="con-img" :src="mine.url" mode=""></image>
				<view class="con-right">
					<view class="con-title">{{mine.title}}</view>
					<view class="con-status" :class="mine.status==2?'status-not':mine.status==3?'status-finish':'status-doing'">{{mine.status==1?'课程进行中':mine.status==2?'课程未开始':'已完成本阶段，可进入下一阶段学习'}}</view>
				</view>
			</view>
			
		</view>
		<view class="lesson-box">
			<view class="mine-lesson">
				<view class="mine-title">
					最新课程
				</view>
				<view class="more-title">
					更多
				</view>
			</view>
			<view class="new-lesson" v-for="item in newData" :key="index">
				<image class="new-img" :src="item.url" mode=""></image>
				<view class="con-right new-right">
					<view class="con-title">{{item.title}}</view>
					<view class="brief">{{item.brief}}</view>
					<view class="author">
						<text>{{item.anthor}}</text>
						<text>{{item.date}}</text>
					</view>
				</view>
			</view>

		</view>
	</view>
</template>

<script setup lang="ts">
	interface ColumnProps {
		id: number;
		title: string;
		icon: string;
	}
	interface MineLessonList{
		title:string;
		url:string;
		status:number
	}
	interface newLessonList{
		title:string;
		url:string;
		brief:string;
		anthor:string;
		date:number
	}
	const navData: ColumnProps[] = [{
			id: 1,
			title: "文化咖啡厅",
			icon: "/static/home/coffee.png"
		},
		{
			id: 2,
			title: "亲密之旅",
			icon: "/static/home/heart.png"
		},
		{
			id: 3,
			title: "以弗得",
			icon: "/static/home/coat.png"
		},
		{
			id: 4,
			title: "我的课程",
			icon: "/static/home/hat.png"
		},
	]
	const mineData: MineLessonList[]=[{
		title:"课程标题",
		url:"/static/home/hat.png",
		status:1
	},{
		title:"课程标题",
		url:"/static/home/hat.png",
		status:2
	},{
		title:"课程标题",
		url:"/static/home/hat.png",
		status:3
	}]
	const newData: newLessonList[]=[{
		title:"课程标题",
		url:"/static/home/hat.png",
		brief:"简介：1222222222223",
		anthor:"消化",
		date:2022-12-9
	},{
		title:"课程标题",
		url:"/static/home/hat.png",
		brief:"简介：1222222222223",
		anthor:"呵呵",
		date:2022-12-9
	},{
		title:"课程标题",
		url:"/static/home/hat.png",
		brief:"简介：1222222222223",
		anthor:"嘻嘻",
		date:2022-12-9
	}]
</script>

<style>
	.head {
		display: flex;
		align-items: center;
		justify-content: space-around;
		padding: 16px 0;
		margin: 20px;
		background: #000;
		box-shadow: 0px 2px 6px 0px rgba(0, 123, 199, 0.08);
		border-radius: 12px;
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

	.mainbox {
		padding: 20px;
	}

	.mine-lesson {
		display: flex;
		align-items: center;
		justify-content: space-between;
		background-image: url(/static/home/dec.png), url(/static/home/arrow.png);
		background-repeat: no-repeat, no-repeat;
		background-position: left top, right center;
		background-size: 6px 100%, 6px 10px;
		margin-bottom: 20px;
	}

	.mine-title {
		color: #007BC7;
		line-height: 22px;
		font-size: 16px;
		padding-left: 14px;

	}

	.more-title {
		font-size: 14px;
		color: #AEB3B7;
		padding-right: 10px;
	}

	.content-box {
		display: flex;
		align-items: center;
		margin-bottom: 30px;
	}

	.con-img {
		width: 48px;
		height: 48px;
		box-shadow: 0px 2px 4px 0px #D2D5D7;
		border-radius: 30px;
		margin-right: 8px;

	}

	.con-right {
		display: flex;
		flex-direction: column;
		align-content: space-between;
	}

	.con-title {
		font-size: 14px;
		color: #3A3C3D;
		line-height: 20px;
		width: 300px;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}

	.con-status {
		font-size: 12px;
		color: rgba(0, 123, 199, 0.8);
		line-height: 20px;
	}

	.status-not {
		color: #AEB3B7;
	}

	.status-finish {
		color: #FDBF08;
	}

	.status-doing {
		color: rgba(0, 123, 199, 0.8);

	}

	.new-lesson {
		display: flex;
		margin-bottom: 50px;
	}

	.new-img {
		width: 56px;
		height: 76px;
		box-shadow: 0px 2px 4px 0px #D2D5D7;
		border-radius: 4px;
		margin-right: 8px;
	}

	.brief {
		display: -webkit-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
		font-size: 12px;
	}

	.author {
		display: flex;
		justify-content: space-between;
		color: #007BC7;
		font-size: 12px;
		line-height: 20px;
	}
</style>
