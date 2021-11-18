<template>
    <v-row justify="center" align="center">
      <v-col cols="12" sm="8" md="6">
        <v-card>
          <v-card-title class="justify-center font-bold primary">
            文字数チェッカー
          </v-card-title>
        </v-card>
        <v-card class="logo py-4 d-flex justify-center">
          <v-textarea
            v-model="inputText"
            name=""
            label="入力欄"
            value="文字数をカウントするテキストを入力して下さい。"
            hint="こちらにテキストを入力して下さい。"
          ></v-textarea>
        </v-card>
          <p class="char-box">文字数: <span>{{ textCount }}</span> </p>
          <button class="btn-reset" @click="reset">リセット</button>
      </v-col>
    </v-row>
</template>

<script>
export default{
  data(){
    return {
      inputText: ''
    };
  },
  computed:{
    textCount(){
      const noSpace =this.inputText.replace(/\s+/g, "");
      return noSpace.length
    },
  },
  methods:{
  reset(){
    this.inputText = ''
  }
}
}
</script>
