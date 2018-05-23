<template>
  <div id="app">
    <h1>在线翻译！！</h1>
    <h5>简单 / 易用 / 便捷</h5>
    <translateform v-on:formSubmit="translateText"></translateform>
    <br>
    <translateoutput v-text="translatedText"></translateoutput>
  </div>
</template>

<script>
import TranslateOutput from './components/TranslateOutput'
import TranslateForm from './components/TranslateForm'


export default {
  name: 'App',
  data:function () {
    return {
      translatedText:"",
    }
  },
  components: {
    "translateoutput":TranslateOutput,
    "translateform":TranslateForm
  },
  methods:{
    translateText:function (text,language) {
      // alert(text)
      this.$http.get("https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180409T153822Z.d280671cbef7af6c.ac225f6cd0d91dfaaab1a14b1a1f7347b4b95f78&lang="+language+"&text="+text)
        .then((response)=>{
          this.translatedText = response.body.text[0]
        })
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
