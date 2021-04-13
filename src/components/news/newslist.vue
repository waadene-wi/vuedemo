<template>
	<div id="tmpl">
		<ul class="mui-table-view">
			<li class="mui-table-view-cell mui-media" v-for="item in list">
				<a href="javascript:;">
					<img class="mui-media-object mui-pull-left" src="../../../statics/imgs/1.png" height="119" width="120">
					<div class="mui-media-body">
						幸福
						<p class='mui-ellipsis'><span>发表时间：</span><span class="click">点击：</span></p>
					</div>
				</a>
			</li>
		</ul>
	</div>
</template>

<script>
// import { Toast } from 'mint-ui';
// import common from '../kits/common.js';

// 	export default({
// 		data(){
// 			return {
// 				list:[],
// 			}
// 		},
// 		created(){
// 			this.getData(),
// 		},
// 		methods:{
// 			getData(){
// 				var url = common.apidomain+"/api/getnewslist";
// 				this.$http.get(url).then(function(res){
// 					if (res.body.status!=0) {
// 						Toast(res.body.message);
// 						return
// 					}
// 					this.list = res.body.message;
// 				})
// 			}
// 		}
// 	})
	
</script>

<style scoped>
	.mui-table-view .mui-media-object{
		width: 70px;
		height: 70px;
		max-width: 70px;
		line-height: 70px;
	}
	.mui-table-view .mui-ellipsis{
		margin-top: 1.5em;
	}
	.mui-table-view .mui-ellipsis .click{
		float: right;
	}

</style>