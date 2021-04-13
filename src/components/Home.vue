<template>
	<div id="tmpl">
	 <!-- 1.0 轮播图：mint-ui中的 swipe组件实现 -->
		 <mt-swipe :auto="4000">
		  <!-- <mt-swipe-item>1</mt-swipe-item>
		   -->
		   <mt-swipe-item v-for="item in list">
		   <img :src="item.img"></mt-swipe-item>
		   
		</mt-swipe>

		<!-- 2.0 利用MUI的9宫格样式实现导航区域 -->
		<div class="mui-content">
		        <ul class="mui-table-view mui-grid-view mui-grid-9">
		            <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#/news/newslist">
		                    <span class="mui-icon mui-icon-home"></span>
		                    <div class="mui-media-body">新闻资讯</div></router-link></li>
		            <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#">
		                    <span class="mui-icon mui-icon-email"></span>
		                    <div class="mui-media-body">图片分享</div></router-link></li>
		            <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#">
		                    <span class="mui-icon mui-icon-chatbubble"></span>
		                    <div class="mui-media-body">商品购买</div></router-link></li>
		            <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#">
		                    <span class="mui-icon mui-icon-location"></span>
		                    <div class="mui-media-body">留言反馈</div></router-link></li>
		            <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#">
		                    <span class="mui-icon mui-icon-search"></span>
		                    <div class="mui-media-body">视频专区</div></router-link></li>
		            <li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3"><router-link to="#">
		                    <span class="mui-icon mui-icon-phone"></span>
		                    <div class="mui-media-body">联系我们</div></router-link></li>
		           
		        </ul> 
		</div>
	

	</div>
</template>

<script>

import { Toast } from 'mint-ui';
import common from '../kits/common.js';
export default{
	data(){
		return{
			list:[]
		}
	},
	created(){
		// this.getData()
	},
	methods:{
		getData(){
			var url = common.apidomain + '/api/getlunbo';
			this.$http.get(url).then(function(res){
				var data = res.body;
				if (data.status!=0) {
					Toast(data.message);
					return;
				}
				this.list = data.message;
			})
		}
	}
}

</script>

<style scoped>
	.mint-swipe{
		height: 200px;
		background-color: red;
	}
	.mui-content .mui-grid-view{
		background-color: white;
		border:0;
	}
	.mui-content .mui-grid-view .mui-table-view-cell{
			border:0;
	}
	.mui-icon-home:before,
	.mui-icon-email:before,
	.mui-icon-chatbubble:before,
	.mui-icon-location:before,
	.mui-icon-search:before,
	.mui-icon-phone:before{
		content: '';
		display: inline-block;
		width: 50px;
		height: 50px;
		background-repeat: round;
	}
	
	.mui-icon-home:before{		
		background-image: url(../../statics/imgs/1.png);
	}

	.mui-icon-email:before{		
		background-image: url(../../statics/imgs/2.png);		
	}
	.mui-icon-chatbubble:before{		
		background-image: url(../../statics/imgs/3.png);		
	}
	.mui-icon-location:before{		
		background-image: url(../../statics/imgs/4.png);		
	}
	.mui-icon-search:before{		
		background-image: url(../../statics/imgs/5.png);		
	}
	.mui-icon-phone:before{		
		background-image: url(../../statics/imgs/6.png);		
	}

</style>