<template>
  <div class="row" id="translateForm">
	  <div class="col-md-offset-3 col-md-6">
	
		  <form class="jumbotron form-inline" v-on:submit='formSubmit'>
			<input class="form-control" type='text' v-model='textToTranslate' placeholder='Input what you want to translate,please.'>
			<select class="form-control osele" v-model='lang'>
				<option value='en'>英文</option>
				<option value='zh'>中文</option>

			</select>
			<input class="btn btn-primary obtn" type='submit' value='Translate'>
		</form>
	</div>
  </div>
</template>

<script>

	export default {
	  name: 'translateForm',
	  data:function(){
		return {
			textToTranslate:'',
			lang:'en'
		}
	  },
	  methods:{
		formSubmit:function(e){
			this.$emit('formSub', this.textToTranslate,this.lang); //$emit(父组件中接受的值,data) 子组件向父组件传值
			e.preventDefault(); // 禁用默认事件
		}
	  }
	}
</script>

<style>
	.osele{
		margin-left: 10px;
	}
	.obtn{
		margin-left: 10px;
	}
</style>
