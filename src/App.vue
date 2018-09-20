<template>
  <div id="app">
    <h2 class="text-muted">TRANSLATE</h2>
    <translateForm v-on:formSub='translateText'></translateForm>
    <translateOutput v-bind:arrayTranslate='arrayTranslate'></translateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'app',
  data() {
    return{
			arrayTranslate:''
	}
  },
  components: {
    TranslateForm,
    TranslateOutput
  },
  methods:{
    translateText:function(text,language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?lang='+language+'&text='+text+'&key=trnsl.1.1.20180920T020329Z.c860e35a3fac64cf.4a81a9c49d672ee6730ce1579358e62676a90a87')
        .then((response)=>{
        if(response.status === 200){
//        for(let text of response.body.text){
			this.arrayTranslate = response.body.text                                                                                                                                                                                                                                                        
			console.log(this.arrayTranslate)
            
       // }

        }
      });
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
