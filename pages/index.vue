<template>
  <v-app>
        <v-card class="elevation-0 rounded-t indigo lighten-5">
          <v-card-text class="pb-0">
            <p class="text-center text-h6 font-weight-black">
              <v-icon>mdi-clipboard-check-outline</v-icon>
            文字数チェッカー
            </p>
          </v-card-text>
        </v-card>
        <v-container class="mt-0">
        <v-card class="elevation-0 mb-3 rounded indigo darken-4">
          <v-card-text class="pb-1">
            <p class="text-center text-h6 white--text font-weight-black">
            テキスト入力欄
            </p>
          </v-card-text>
        </v-card>
            <v-card class="elevation-0 pb-0">
              <v-textarea
                v-model="inputText"
                name="input"
                background-color="indigo lighten-5"
                filled
                auto-grow
                hint="※こちらにテキストを入力して下さい。"
              ></v-textarea>
            </v-card>
            <v-row>
              <v-col cols="auto" class="mr-auto">
              <p class="char-box font-weight-black"><strong class="orange--text text--darken-3">文字数 : <span>{{ textCount }}</span></strong></p>
              </v-col>
              <v-col cols="auto">
              <v-btn class="mr-8 elevation-0 rounded indigo darken-4 white--text font-weight-black" @click="reset">リセット</v-btn>
              </v-col>
            </v-row>
              
        </v-container>
  </v-app>
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
