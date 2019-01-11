<template>
<div id="app">
 <mt-header title="手机通讯录">
		  <mt-button icon="back" slot="left">返回</mt-button>
			<mt-button icon="more" slot="right"></mt-button>
			<!-- 在脚手架的基础上安装 npm install mint-ui -S  脚手架安装详细见【nodejs脚手架安装】文档
			 然后 
			 // 引入全部组件
					import Vue from 'vue';
					import Mint from 'mint-ui';
					Vue.use(Mint); 
					详细见：mint-ui文档
					https://mint-ui.github.io/#!/zh-cn-->
		</mt-header>
				<mt-index-list>
						<mt-index-section v-for="item in userDatas" v-bind:index="item.index" :key = "item.id">
								<mt-cell v-for="user in item.users" @click.native="telAlert(user.tel)" :title="user.name" :key = "user.id"></mt-cell>
						</mt-index-section>
				</mt-index-list>
		</div>
</template>

<script>
	import { MessageBox } from 'mint-ui';
var userDatas = [
				{'index':'A','users':[
					{'name':'曹操','tel':'15908895071'},
					{'name':'刘玄德','tel':'15908895072'},
					{'name':'张梓琳','tel':'15908895073'}
				]},
				{'index':'B','users':[
					{'name':'陈瑶','tel':'15908895074'},
					{'name':'吾爱','tel':'15908895075'},
					{'name':'周迅','tel':'15908895076'}
				]},
				{'index':'C','users':[
					{'name':'周亚明','tel':'15908895077'},
					{'name':'周杰伦','tel':'15908895078'},
					{'name':'康佳乐','tel':'15908895079'}
				]},
				{'index':'D','users':[
					{'name':'Jackson','tel':'15908895081'},
					{'name':'猫儿','tel':'15908895082'},
					{'name':'杰克','tel':'15908895083'}
				]},
				{'index':'E','users':[
					{'name':'钟丽缇','tel':'15908895084'},
					{'name':'肖亚讯','tel':'15908895085'},
					{'name':'陈朝霞','tel':'15908895086'}
				]},
				{'index':'F','users':[
					{'name':'李文华','tel':'15908895087'},
					{'name':'赵宇','tel':'15908895088'},
					{'name':'菲菲','tel':'15908895089'}
				]}
				];
export default {
  name: 'App',
	data(){
		return{
			userDatas:userDatas
		}
	},
	methods:{
		telAlert:function(tel){
			MessageBox({
					title: '呼叫',
					message: tel,
					showCancelButton: true,
					//该方法会返回一个promise对象，因此这里要接收，then方法
}).then(function(){alert('成功')});
			
		}
	}
}
</script>

<style>
*{margin: 0;padding: 0;}
</style>
