<template>
  <div class="row" id="translateForm" style=" padding-left: 3%;">
    <div class="col-md-12 col-md-offset-3">
      <form id="transForm" class="form-inline well" v-on:submit="formSubmit">
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="Entrez vos mots">
        <select class="form-control" v-model="language" style="margin-left:30px;">
          <option value="ru">Russian</option>
          <option value="es">Spanish</option>
          <option value="fr">French</option>
          <option value="zh">Chinese</option>
        </select>
        <input class="btn btn-primary" type="submit" style="margin-left:30px;" value="Traduire">
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'translateForm',
  data(){
    return {
      textToTranslate:'',
      language:''
    }
  },
  created() {
    this.language = 'ru';
  },
  methods: {
    formSubmit(e){
      this.$emit('formSubmit', this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
}
</script>

<style>
  #transForm{
    border-radius:10px;
    width: 25%;
   
    /* background-color: aquamarine; */
    margin: 0 auto;
    /* border: 1px #ccc solid; */
  }
</style>
