<template>
	<view class="content">
		<form class="app-update-pv">
			
									<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">购买单号</view>
				<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="right-input">
					{{ruleForm.goumaidanhao}}
				</view>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0","borderStyle":"solid","height":"108rpx"}' class="cu-form-group select">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品编号</view>
				<picker @change="shangpinbianhaoChange" :value="shangpinbianhaoIndex" :range="shangpinbianhaoOptions">
					<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="uni-input">{{shangpinbianhaoOptions[shangpinbianhaoIndex]}}</view>
				</picker>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品名称</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.shangpinmingcheng" v-model="ruleForm.shangpinmingcheng" placeholder="商品名称"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">商品类别</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.shangpinleibie" v-model="ruleForm.shangpinleibie" placeholder="商品类别"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0.1)","borderColor":"#ccc","margin":"0 0 20rpx 0","borderWidth":"0","borderStyle":"solid","height":"160rpx"}' class="cu-form-group" @tap="tupianTap" :class='right == "left"?"":"active"'>
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(51, 51, 51, 1)","textAlign":"center"}' class="title">图片</view>
				<view class="right-input" :style='{textAlign:"right"}' style="padding:0">
					<image :style='{"width":"120rpx","boxShadow":"0 0 8rpx rgba(0,0,0,.3)","borderRadius":"40rpx","textAlign":"right","height":"120rpx"}' class="avator" v-if="ruleForm.tupian" :src="ruleForm.tupian" mode="aspectFill"></image>
					<image :style='{"width":"120rpx","boxShadow":"0 0 8rpx rgba(0,0,0,.3)","borderRadius":"40rpx","textAlign":"right","height":"120rpx"}' class="avator" v-else src="../../static/gen/upload.png" mode="aspectFill"></image>
				</view>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">出售单价</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.chushoudanjia" v-model="ruleForm.chushoudanjia" placeholder="出售单价"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">购买数量</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.goumaishuliang" v-model="ruleForm.goumaishuliang" placeholder="购买数量"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">购买总价</view>
				<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="right-input">
					{{goumaizongjia}}
				</view>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0","borderStyle":"solid","height":"108rpx"}' class="cu-form-group select">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">购买时间</view>
				<picker mode="date" :value="ruleForm.goumaishijian" @change="goumaishijianChange">
					<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' class="uni-input">{{ruleForm.goumaishijian?ruleForm.goumaishijian:"请选择购买时间"}}</view>
				</picker>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">用户名</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.yonghuming" v-model="ruleForm.yonghuming" placeholder="用户名"></input>
			</view>
												<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0","borderWidth":"0 ","borderStyle":"solid","height":"108rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">姓名</view>
				<input :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"80rpx"}' :disabled="ro.xingming" v-model="ruleForm.xingming" placeholder="姓名"></input>
			</view>
																																				
			<!-- 否 -->
 
			
			          				          				          				          				          				          				          				          				          				          				          				          				          				          							
			          				          				          				          				          				          				          				          				          				          				          				          				<view :style='{"boxShadow":"0 0 0px rgba(0,0,0,.3)","backgroundColor":"rgba(1, 157, 214, 0)","borderColor":"rgba(245, 245, 245, 1)","margin":"0 0 0 0","borderWidth":"0","borderStyle":"solid","height":"308rpx"}' class="cu-form-group">
				<view :style='{"width":"160rpx","fontSize":"28rpx","color":"rgba(68, 68, 68, 1)","textAlign":"center"}' class="title">备注</view>
				<textarea :style='{"boxShadow":"0 0 0px rgba(0,0,0,.6) inset","backgroundColor":"rgba(255, 255, 255, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"0","color":"rgba(68, 68, 68, 1)","textAlign":"left","borderWidth":"2rpx","fontSize":"26rpx","borderStyle":"solid","height":"280rpx"}' v-model="ruleForm.beizhu" placeholder="备注"></textarea>
			</view>
						          				          							
			<view class="btn">
				<button :style='{"boxShadow":"0 0 0px rgba(0,0,0,0) inset","backgroundColor":"rgba(113, 186, 0, 1)","borderColor":"rgba(68, 68, 68, 1)","borderRadius":"8rpx","color":"#fff","borderWidth":"2rpx","width":"90%","fontSize":"32rpx","borderStyle":"solid","height":"80rpx"}' @tap="onSubmitTap" class="bg-red">提交</button>
			</view>
		</form>

																																																													
	</view>
</template>

<script>
	import wPicker from "@/components/w-picker/w-picker.vue";

	export default {
		data() {
			return {
				ruleForm: {
												goumaidanhao: this.getUUID(),
																shangpinbianhao: '',
																shangpinmingcheng: '',
																shangpinleibie: '',
																tupian: '',
																chushoudanjia: '',
																goumaishuliang: '',
																goumaizongjia: '',
																goumaishijian: '',
																yonghuming: '',
																xingming: '',
																beizhu: '',
																ispay: '',
																userid: '',
												},
																				shangpinbianhaoOptions: [],
				shangpinbianhaoIndex: 0,
																																																																																																												// 登陆用户信息
				user: {},
                                ro:{
                                   goumaidanhao : false,
                                   shangpinbianhao : false,
                                   shangpinmingcheng : false,
                                   shangpinleibie : false,
                                   tupian : false,
                                   chushoudanjia : false,
                                   goumaishuliang : false,
                                   goumaizongjia : false,
                                   goumaishijian : false,
                                   yonghuming : false,
                                   xingming : false,
                                   beizhu : false,
                                   ispay : false,
                                   userid : false,
                                },
			}
		},
		components: {
			wPicker
		},
		computed: {
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						goumaizongjia:{
																																																																																																																get: function () {
				return 1*this.ruleForm.chushoudanjia*this.ruleForm.goumaishuliang
			}
			},
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
						
					},
		async onLoad(options) {
			let table = uni.getStorageSync("nowTable");
			// 获取用户信息
			let res = await this.$api.session(table);
			this.user = res.data;
			
						// ss读取
																																																															this.ruleForm.yonghuming = this.user.yonghuming
												this.ruleForm.xingming = this.user.xingming
																											
																		// 下2
			res = await this.$api.option(`shangpinxinxi`,`shangpinbianhao`,{});
			this.shangpinbianhaoOptions = res.data;
																																																																																	
			// 如果有登陆，获取登陆后保存的userid
			this.ruleForm.userid = uni.getStorageSync("userid")
			if (options.refid) {
				// 如果上一级页面传递了refid，获取改refid数据信息
				this.ruleForm.refid = options.refid;
				this.ruleForm.nickname = uni.getStorageSync("nickname");
			}
			// 如果是更新操作
			if (options.id) {
				this.ruleForm.id = options.id;
				// 获取信息
				res = await this.$api.info(`goumaijilu`, this.ruleForm.id);
				this.ruleForm = res.data;
			}
			// 跨表
			if(options.cross){
				var obj = uni.getStorageSync('crossObj');
				for (var o in obj){
					if(o=='goumaidanhao'){
					this.ruleForm.goumaidanhao = obj[o];
					this.ro.goumaidanhao = true;
					continue;
					}
					if(o=='shangpinbianhao'){
					this.ruleForm.shangpinbianhao = obj[o];
					this.ro.shangpinbianhao = true;
					continue;
					}
					if(o=='shangpinmingcheng'){
					this.ruleForm.shangpinmingcheng = obj[o];
					this.ro.shangpinmingcheng = true;
					continue;
					}
					if(o=='shangpinleibie'){
					this.ruleForm.shangpinleibie = obj[o];
					this.ro.shangpinleibie = true;
					continue;
					}
					if(o=='tupian'){
					this.ruleForm.tupian = obj[o];
					this.ro.tupian = true;
					continue;
					}
					if(o=='chushoudanjia'){
					this.ruleForm.chushoudanjia = obj[o];
					this.ro.chushoudanjia = true;
					continue;
					}
					if(o=='goumaishuliang'){
					this.ruleForm.goumaishuliang = obj[o];
					this.ro.goumaishuliang = true;
					continue;
					}
					if(o=='goumaizongjia'){
					this.ruleForm.goumaizongjia = obj[o];
					this.ro.goumaizongjia = true;
					continue;
					}
					if(o=='goumaishijian'){
					this.ruleForm.goumaishijian = obj[o];
					this.ro.goumaishijian = true;
					continue;
					}
					if(o=='yonghuming'){
					this.ruleForm.yonghuming = obj[o];
					this.ro.yonghuming = true;
					continue;
					}
					if(o=='xingming'){
					this.ruleForm.xingming = obj[o];
					this.ro.xingming = true;
					continue;
					}
					if(o=='beizhu'){
					this.ruleForm.beizhu = obj[o];
					this.ro.beizhu = true;
					continue;
					}
					if(o=='userid'){
					this.ruleForm.userid = obj[o];
					this.ro.userid = true;
					continue;
					}
				}
			}
			this.styleChange()
		},
		methods: {
			styleChange() {
				this.$nextTick(()=>{
					// document.querySelectorAll('.app-update-pv .cu-form-group .uni-input-input').forEach(el=>{
					//   el.style.backgroundColor = this.addUpdateForm.input.content.backgroundColor
					// })
				})
			},
																		// 下二随
			async shangpinbianhaoChange (e) {
				this.shangpinbianhaoIndex = e.target.value
				this.ruleForm.shangpinbianhao = this.shangpinbianhaoOptions[this.shangpinbianhaoIndex]
				let res = await this.$api.follow(`shangpinxinxi`, `shangpinbianhao`,{
					columnValue: this.ruleForm.shangpinbianhao
				});
																												if(res.data.shangpinmingcheng){
					this.ruleForm.shangpinmingcheng = res.data.shangpinmingcheng
				}
																if(res.data.shangpinleibie){
					this.ruleForm.shangpinleibie = res.data.shangpinleibie
				}
																								if(res.data.chushoudanjia){
					this.ruleForm.chushoudanjia = res.data.chushoudanjia
				}
																																																																											},
																																																																														
			// 多级联动参数
																																																																																										
																																																									goumaishijianChange(e) {
				this.ruleForm.goumaishijian = e.target.value;
				this.$forceUpdate();
			},
																																				
																																																																																							
																																																																																							
																																													tupianTap() {
				let _this = this;
				this.$api.upload(function(res) {
					_this.ruleForm.tupian = _this.$base.url + 'upload/' + res.file;
					_this.$forceUpdate();
					_this.$nextTick(()=>{
						_this.styleChange()
					})
				});
			},
																																																																																										
			getUUID () {
				return new Date().getTime();
			},
			async onSubmitTap() {
																																																																				this.ruleForm.goumaizongjia = this.goumaizongjia
																																																																																																																																																																																																																																																																																																																																																																																																																																																																																								if((!this.ruleForm.goumaidanhao)){
					this.$utils.msg(`购买单号不能为空`);
					return
				}
																																												if((!this.ruleForm.shangpinbianhao)){
					this.$utils.msg(`商品编号不能为空`);
					return
				}
																																																																																																																																																												if(this.ruleForm.chushoudanjia&&(!this.$validate.isIntNumer(this.ruleForm.chushoudanjia))){
					this.$utils.msg(`出售单价应输入整数`);
					return
				}
																																												if(this.ruleForm.goumaishuliang&&(!this.$validate.isIntNumer(this.ruleForm.goumaishuliang))){
					this.$utils.msg(`购买数量应输入整数`);
					return
				}
																																												if(this.ruleForm.goumaizongjia&&(!this.$validate.isIntNumer(this.ruleForm.goumaizongjia))){
					this.$utils.msg(`购买总价应输入整数`);
					return
				}
																																																																																																																																																																																																																																																												if(this.ruleForm.id){
					await this.$api.update(`goumaijilu`, this.ruleForm);
				}else{
					await this.$api.add(`goumaijilu`, this.ruleForm);
				}
				this.$utils.msgBack('提交成功');
			},
			optionsChange(e) {
				this.index = e.target.value
			},
			bindDateChange(e) {
				this.date = e.target.value
			},
			getDate(type) {
				const date = new Date();
				let year = date.getFullYear();
				let month = date.getMonth() + 1;
				let day = date.getDate();
				if (type === 'start') {
					year = year - 60;
				} else if (type === 'end') {
					year = year + 2;
				}
				month = month > 9 ? month : '0' + month;;
				day = day > 9 ? day : '0' + day;
				return `${year}-${month}-${day}`;
			},
			toggleTab(str) {
				this.$refs[str].show();
			}
		}
	}
</script>

<style lang="scss" scoped>
	.container {
		padding: 20upx;
	}
	
	.content:after {
		position: fixed;
		top: 0;
		right: 0;
		left: 0;
		bottom: 0;
		content: '';
				background-image: url(http://codegen.caihongy.cn/20210329/bac17293dec74a61b63867efe3bb6be6.png);
				background-attachment: fixed;
		background-size: cover;
		background-position: center;
	}

	textarea {
		border: 1upx solid #EEEEEE;
		border-radius: 20upx;
		padding: 20upx;
	}

	.title {
		width: 180upx;
	}

	.avator {
		width: 150upx;
		height: 60upx;
	}

	.right-input {
		flex: 1;
		text-align: left;
		padding: 0 24upx;
	}
	
	.cu-form-group.active {
		justify-content: space-between;
	}
	
	.btn {
	  display: flex;
	  align-items: center;
	  justify-content: center;
	  flex-wrap: wrap;
	  padding: 20upx 0;
	}
	
	.cu-form-group {
		padding: 0 24upx;
		background-color: transparent;
		min-height: inherit;
	}
	
	.cu-form-group+.cu-form-group {
		border: 0;
	}
	
	.cu-form-group uni-input {
		padding: 0 30upx;
	}
	
	.uni-input {
		padding: 0 30upx;
	}
	
	.cu-form-group uni-textarea {
		padding: 30upx;
		margin: 0;
	}
	
	.cu-form-group uni-picker::after {
		line-height: 80rpx;
	}
	
	.select .uni-input {
		line-height: 80rpx;
	}
	
	.input .right-input {
		line-height: 80rpx;
	}
</style>
