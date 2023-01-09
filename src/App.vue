<template>
  <div class="container">
    <div class="row my-5  justify-content-center">
      <div class="col-md-12">
        <h4 class="my-4 text-center">Keywords Textbox</h4>
      </div>
      <div class="col-md-4">
        <label for="text" class="mb-2">Type Keyword and Seperate Them by Comma Symbol (,)  </label>
        <input type="text" v-model="textInput" @keyup="textChanged" class="text-input mb-4 w-100">
        <span class="keyword-item" v-for="item in keywords" :key="item">{{ item }}</span>
      </div>
    </div>

  </div>

</template>
<script >
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'App',
  components: {

  },
  data: function () {
    return {
      keywords: [],
      textInput: ''
    }

  },
  mounted() {
    console.log('Mounted');
  },
  methods: {
    textChanged() {
      if (this.textInput.indexOf(',') > 0 && this.textInput.length) {
        let keyword = this.textInput.replace(',', '')
        this.keywords.push(keyword);
        this.textInput = ''
      }
    }
  }
});

</script>
<style>
.keyword-item {
  display: inline-block;
  margin-top: 5px;
  margin-right: 7px;
  background-color: rgb(219, 219, 219);
  padding: 4px;
  border-radius: 4px;
}

</style>
