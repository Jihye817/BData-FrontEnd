<template>
  <v-container fluid>
    <v-col cols="12" align="center">
      <v-row class="login_wrap">
        <v-col cols="12">
          <v-row>
            B-Data
          </v-row>
          <v-row class="pt-3 pb-1">
            <input class="text_input">
          </v-row>
          <v-row class="pb-3">
            <input class="text_input">
          </v-row>
          <v-row>
            <v-btn elevation="0" class="login_btn">로그인</v-btn>
          </v-row>
          <v-row class="pt-1" justify="space-between">
            <v-col cols="auto">
              <a href="">아이디/비밀번호 찾기</a>
            </v-col>
            <v-col cols="auto">
              <RouterLink to="/register">회원가입</RouterLink>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-col>
  </v-container>
</template>

<script setup>
import { RouterLink } from 'vue-router'

</script>

<style scoped>
.login_wrap {
  width: 400px;
}
.login_wrap > .v-col > .v-row {
  justify-content: center;
}
.text_input {
  border: 1px solid grey;
  border-radius: 5px;
  width: 100%;
  padding: 10px;
}
.login_btn {
  width: 100%;
  background-color: teal;
  color: white;
  height: 45px;
}
</style>