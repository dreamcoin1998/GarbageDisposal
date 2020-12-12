<template>
	<view class="content">
		<view class="text-area">
			<text class="title">{{title + options[selecValue].garbageNum}}</text>
		</view>
		<view class="chart">
			<image class="histogram" :src="options[selecValue].histogram" mode=""></image>
			<easy-select
				class="select"
				ref="easySelect"
				size="small"
				:value="options[selecValue].label"
				:options="options"
				@selectOne="selectOne">
			</easy-select>
			<image class="piechart" :src="options[selecValue].piechart" mode=""></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: '回收垃圾总数：',
				selecValue: 0,
				options: [{
					"value": 0,
					"label": "合江街道",
					"histogram": "../../static/garbageClassification/histogram_0.png",
					"piechart": "../../static/garbageClassification/piechart_0.png",
					"garbageNum": 216
				},{
					"value": 1,
					"label": "青山街道",
					"histogram": "../../static/garbageClassification/histogram_1.png",
					"piechart": "../../static/garbageClassification/piechart_1.png",
					"garbageNum": 100
				},{
					"value": 2,
					"label": "人民街道",
					"histogram": "../../static/garbageClassification/histogram_2.png",
					"piechart": "../../static/garbageClassification/piechart_2.png",
					"garbageNum": 145
				},{
					"value": 3,
					"label": "黄沙湾街道",
					"histogram": "../../static/garbageClassification/histogram_3.png",
					"piechart": "../../static/garbageClassification/piechart_3.png",
					"garbageNum": 199
				},{
					"value": 4,
					"label": "潇湘街道",
					"histogram": "../../static/garbageClassification/histogram_4.png",
					"piechart": "../../static/garbageClassification/piechart_4.png",
					"garbageNum": 76
				},{
					"value": 5,
					"label": "五一街道",
					"histogram": "../../static/garbageClassification/histogram_5.png",
					"piechart": "../../static/garbageClassification/piechart_5.png",
					"garbageNum": 202
				}]
			}
		},
		onLoad() {

		},
		methods: {
			selectOne(options) {
				this.selecValue = options.value
			},
			useOutClickSide() {
				this.$refs.easySelect.hideOptions && this.$refs.easySelect.hideOptions()
			}
		}
	}
</script>

<style>
	.text-area {
		margin-top: 40rpx;
		margin-left: 40rpx;
		font-size: 36rpx;
	}
	.chart {
		width: 100%;
		margin-top: 66rpx;
		text-align: center;
	}
	.histogram {
		width: 667rpx;
		margin: auto;
	}
	.piechart {
		width: 100%;
		margin: auto;
		margin-top: 40rpx;
	}
	.select {
		display: block;
		margin-top: 40rpx;
		display: inline-block;
	}
</style>
