<template>
	<view class="container">
		<image class="logo" src="@/static/书果logo竖版png@1x.png"></image>
		<text class="system-name">书果星球门店管理</text>

		<button class="login-button" @click="showLoginPopup">系统登录</button>

		<!-- 登录弹窗 -->
		<view v-if="showLogin" class="modal">
			<view class="modal-background" @click="closeLoginPopup"></view>
			<view class="modal-content">
				<view class="modal-header">
					<text class="modal-header-text">账号密码登录</text>
					<text class="modal-close" @click="closeLoginPopup">×</text>
				</view>
				<view class="modal-body">
					<input class="modal-body-input" type="text" placeholder="请输入登录账号" placeholder-class="modal-body-input-placeholder" v-model="username" />
					<input class="modal-body-input" type="password" placeholder="请输入密码" placeholder-class="modal-body-input-placeholder" v-model="password" />
					<button class="login-button-popup" @click="login">登录</button>
					<view class="agreement">
						<checkbox-group @change="checkedAgreement">
							<checkbox class="agreement-checkbox" /> 
						</checkbox-group>
						<text>我已阅读并同意书果星球门店管理</text>
						<text @click="showAgreementPopup" class="agreement-link">隐私政策&nbsp;</text>
						<text>、</text>
						<text @click="showAgreementPopup" class="agreement-link">用户协议</text>
					</view>
				</view>
			</view>
		</view>

		<!-- 用户协议弹窗 -->
		<view v-if="showAgreement" class="modal">
			<view class="modal-background" @click="closeAgreementPopup"></view>
			<view class="modal-content">
				<view class="modal-header">
					<text>用户协议</text>
					<text class="modal-close" @click="closeAgreementPopup">×</text>
				</view>
				<view class="modal-body">
					<scroll-view scroll-y="true" style="max-height: 400px;">
						<text>
							<!-- 在这里填写用户协议的内容 -->
							用户协议内容...
						</text>
					</scroll-view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showLogin: false,
				showAgreement: false,
				username: '',
				password: '',
				agreed: false
			};
		},
		methods: {
			showLoginPopup() {
				this.showLogin = true;
			},
			closeLoginPopup() {
				this.showLogin = false;
			},
			showAgreementPopup() {
				this.showAgreement = true;
			},
			closeAgreementPopup() {
				this.showAgreement = false;
			},
			checkedAgreement() {
				this.agreed = !this.agreed;
			},
			async login() {
				if (!this.username || !this.password) {
					uni.showToast({
						title: '请输入账号和密码',
						icon: 'none'
					});
					return;
				}

				if (!this.agreed) {
					uni.showToast({
						title: '请先阅读并同意用户协议',
						icon: 'none'
					});
					return;
				}

				try {
					const response = await uni.request({
						url: 'https://example.com/api/login', // 替换为你的登录API接口
						method: 'POST',
						data: {
							username: this.username,
							password: this.password
						}
					});

					if (response[1].statusCode === 200) {
						uni.showToast({
							title: '登录成功',
							icon: 'success'
						});
						// 处理登录成功后的逻辑，比如跳转到首页
						uni.redirectTo({
							url: '/pages/home/home' // 替换为你的首页路径
						});
					} else {
						uni.showToast({
							title: '登录失败，请检查账号和密码',
							icon: 'none'
						});
					}
				} catch (error) {
					uni.showToast({
						title: '登录出错，请稍后重试',
						icon: 'none'
					});
				}
			}
		}
	};
</script>

<style>
	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding-top: 160px;

		height: 100vh;
		/* 调整整个容器向下移动 */
	}

	.logo {
		width: 166px;
		height: 114px;
		margin-bottom: 24px;
	}

	.system-name {
		font-family: PingFang SC;
		font-size: 21px;
		font-weight: 500;
		line-height: 16.48px;
		text-align: center;
		letter-spacing: 0px;

		color: #000;
		margin-bottom: 110px;
	}

	.login-button {
		width: 335px;
		height: 44px;

		border-radius: 8px;
		font-family: 思源黑体;
		font-size: 16px;
		font-weight: 500;
		line-height: 44px;
		text-align: center;
		letter-spacing: 0px;

		color: #FFFFFF;

		/* 点缀色 */
		background: #FF8535;
	}


	.agreement {
		display: flex;
		align-items: center;
		margin-top: 13px;
		font-size: 13px;
	}
	
	.agreement-checkbox {
		transform: scale(0.7);
	}

	.agreement-link {
		color: #007AFF;
		text-decoration: underline;
		margin-left: 5px;
		cursor: pointer;
	}

	.popup-content {
		display: flex;
		flex-direction: column;
		padding: 20px;
	}

	.popup-content input {
		margin-bottom: 15px;
		padding: 10px;
		border: 1px solid #ccc;
		border-radius: 5px;
	}

	.popup-content button {
		padding: 10px;
		background-color: #007AFF;
		color: #fff;
		border: none;
		border-radius: 5px;
	}

	.modal {
	  position: fixed;
	  top: 0;
	  left: 0;
	  width: 100%;
	  height: 100%;
	  display: flex;
	  align-items: flex-end; /* 将 modal 内容固定在屏幕底部 */
	  justify-content: center;
	  z-index: 999; /* 确保弹窗在最上层 */
	}
	
	.modal-background {
	  position: absolute;
	  top: 0;
	  left: 0;
	  width: 100%;
	  height: 100%;
	  background-color: rgba(0, 0, 0, 0.5);
	  z-index: -1; /* 确保背景在内容之下 */
	}
	
	.modal-content {
	  width: 100%;
	  height: 380px;
	  background-color: #fff;
	  border-top-left-radius: 10px;
	  border-top-right-radius: 10px;
	  overflow: hidden;
	}
	
	.modal-header {
	  display: flex;
	  justify-content: space-between;
	  align-items: center;
	  padding: 15px;
	  /* background-color: #007AFF; */
	  color: #fff;
	}
	
	.modal-header-text {
		flex: 1;
		font-family: 思源黑体;
		font-size: 18px;
		font-weight: normal;
		line-height: 20px;
		letter-spacing: 0px;
		text-align: center;
		
		color: #606266;
	}
	
	.modal-close {
	  cursor: pointer;
	  /* 909399 */
	  font-size: 28px;
	  padding-bottom: 6px;
	  color: #909399;
	}
	
	.modal-body {
	  padding: 10px;
	}
	
	.modal-body-input {
		width: 92%;
		height: 48px;
		border-radius: 22px;
		opacity: 1;
		
		/* F6F7FB */
		background: #eceef8;
		margin-left: 2%;
		padding-left: 16px;
		margin-bottom: 18px;
	}
	
	.modal-body-input-placeholder {
		color: #888; /* 文字颜色 */
		font-size: 18px; /* 字体大小 */
		/* margin-left: 16px; */
		opacity: 1; /* 透明度，1 表示完全不透明 */
	}
	
	.login-button-popup {
	  
	  color: #fff;
	  
	  font-family: 思源黑体;
	  font-size: 18px;
	  font-weight: 500;
	  text-align: center;
	  letter-spacing: 0px;
	  
	  text-align: center;
	  /* line-height: 50px; */
	  border-radius: 5px;
	  margin-bottom: 15px; /* 将按钮与用户协议之间的距离 */
	  
	  
	  width: 96%;
	  height: 48px;
	  border-radius: 8px;
	  opacity: 1;
	  
	  background: #FF8535;
	}
</style>