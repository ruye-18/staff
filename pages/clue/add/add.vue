<template>
	<view class="container">
		<!-- 头像和姓名输入 -->
		<!-- <view class="header">
			<image class="avatar" src="/static/avatar-placeholder.png"></image>
			<input class="name-input" type="text" placeholder="请输入学员姓名" />
		</view> -->

		<!-- 信息项列表 -->
		<!-- <view class="info-list">
			<view class="info-item" v-for="(item, index) in infoItems" :key="index">
				<text class="label">{{ item.label }}</text>
				<input v-if="item.type === 'input'" class="input" type="text" :placeholder="item.placeholder" />
				<picker v-if="item.type === 'picker'" mode="selector" :range="item.range" :value="item.value"
					class="picker" @change="item.onChange">
					<view class="picker-placeholder">{{ item.placeholder }}</view>
				</picker>
				<picker v-if="item.type === 'date'" mode="date" :value="item.value" class="picker"
					@change="item.onChange">
					<view class="picker-placeholder">{{ item.placeholder }}</view>
				</picker>
			</view>
		</view> -->

		<!-- 备注 -->
		<view class="remarks">
			<textarea class="remarks-input" @blur="bindTextAreaBlur" placeholder="请输入（500字以内）" />
			<text class="remarks-counter">0/500</text>
		</view>
		<!-- 
		<view class="remarks">
			<textarea class="remarks-input" placeholder="请输入（500字以内）" maxlength="500"></textarea>
			
		</view> -->

		<!-- 完成按钮 -->
		<button class="submit-button">完成</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				infoItems: [{
						label: '性别',
						type: 'picker',
						range: ['未知', '男', '女'],
						value: 0,
						placeholder: '请选择',
						onChange: this.onGenderChange
					},
					{
						label: '年龄/生日',
						type: 'input',
						placeholder: '请输入年龄'
					},
					{
						label: '',
						type: 'date',
						value: '',
						placeholder: '出生日期',
						onChange: this.onBirthdayChange
					},
					{
						label: '就读学校',
						type: 'input',
						placeholder: '请输入'
					},
					{
						label: '当前年级',
						type: 'picker',
						range: ['一年级', '二年级', '三年级', '四年级', '五年级', '六年级'],
						value: 0,
						placeholder: '请选择',
						onChange: this.onGradeChange
					},
					{
						label: '爸爸',
						type: 'input',
						placeholder: '手机号'
					},
					{
						label: '妈妈',
						type: 'input',
						placeholder: '手机号'
					},
					{
						label: '家庭住址',
						type: 'input',
						placeholder: '请输入'
					},
					{
						label: '意向级别',
						type: 'picker',
						range: ['高', '中', '低'],
						value: 0,
						placeholder: '请选择',
						onChange: this.onIntentLevelChange
					},
					{
						label: '学生来源',
						type: 'picker',
						range: ['门店咨询', '线上咨询', '其他'],
						value: 0,
						placeholder: '请选择',
						onChange: this.onSourceChange
					},
					{
						label: '标签',
						type: 'input',
						placeholder: '请选择'
					}
				]
			};
		},
		methods: {
			onGenderChange(e) {
				this.infoItems[0].value = e.detail.value;
			},
			onBirthdayChange(e) {
				this.infoItems[2].value = e.detail.value;
			},
			onGradeChange(e) {
				this.infoItems[4].value = e.detail.value;
			},
			onIntentLevelChange(e) {
				this.infoItems[8].value = e.detail.value;
			},
			onSourceChange(e) {
				this.infoItems[9].value = e.detail.value;
			},
			bindTextAreaBlur: function (e) {
				console.log(e.detail.value)
			}
		}
	};
</script>

<style>
	.container {
		width: 100%;
		height: 100vh;
		display: flex;
		flex-direction: column;
		background-color: #fff;
	}

	.header {
		display: flex;
		align-items: center;
		margin-bottom: 20px;
	}

	.avatar {
		width: 60px;
		height: 60px;
		border-radius: 50%;
		margin-right: 10px;
	}

	.name-input {
		flex: 1;
		border: none;
		outline: none;
		font-size: 16px;
	}

	.info-list {
		margin-bottom: 20px;
	}

	.info-item {
		display: flex;
		align-items: center;
		padding: 10px 0;
		border-bottom: 1px solid #eee;
	}

	.label {
		width: 80px;
		font-size: 14px;
		color: #333;
	}

	.input {
		flex: 1;
		border: none;
		outline: none;
		font-size: 14px;
	}

	.picker {
		flex: 1;
	}

	.picker-placeholder {
		color: #999;
		font-size: 14px;
	}

	.remarks {
		display: flex;
		flex-direction: column;
		margin: 0 30px;
	}

	.remarks-input {
		flex: 1;
		width: 100%;
		height: 350rpx;
		border: 1rpx solid #eee;
		font-size: 28rpx;
	}

	.remarks-counter {
		text-align: right;
		font-size: 12px;
		color: #999;
		margin-top: 5px;
	}

	.submit-button {
		width: 90%;
		height: 86rpx;
		margin-left: 5%;
		margin-top: 40rpx;
		opacity: 1;
		background: #FF8535;
		color: #fff;
		font-size: 30rpx;
		padding-top: 5rpx;
		text-align: center;
	}
</style>