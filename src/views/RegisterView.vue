<template>
  <v-container fluid>
    <v-col cols="12" align="center">
      <v-form>
        <v-row class="register_wrap">
          <v-col cols="12">
            <v-row> B-Data </v-row>
            <v-row justify="start" class="label_name">아이디</v-row>
            <v-row class="pt-1 pb-2">
              <input class="text_input" required />
            </v-row>
            <v-row justify="start" class="label_name">비밀번호</v-row>
            <v-row class="pt-1 pb-2">
              <input class="text_input" />
            </v-row>
            <v-row justify="start" class="label_name">비밀번호 확인</v-row>
            <v-row class="pt-1 pb-2">
              <input class="text_input" />
            </v-row>
            <v-row justify="start" class="label_name pt-5">이름</v-row>
            <v-row class="pt-1 pb-2">
              <input class="text_input" />
            </v-row>
            <v-row justify="start" class="label_name">생년월일</v-row>
            <v-row class="pt-1 pb-2" justify="space-between">
              <input cols="auto" class="date_input" placeholder="년" />
              <input cols="auto" class="date_input" placeholder="월" />
              <input cols="auto" class="date_input" placeholder="일" />
            </v-row>
            <v-row justify="start" class="label_name">성별</v-row>
            <v-row class="pt-1">
              <v-radio-group inline>
                <v-radio label="남" value="0"></v-radio>
                <v-radio label="여" value="1"></v-radio>
              </v-radio-group>
            </v-row>
            <v-row justify="start" class="label_name">전화번호</v-row>
            <v-row class="pt-1 pb-2">
              <input class="text_input" placeholder="000-0000-0000" />
            </v-row>
            <v-row justify="start" class="label_name">이메일</v-row>
            <v-row class="pt-1 pb-2" justify="space-between" align="center">
              <input class="text_input" style="width: 45%" />
              @
              <input class="text_input" style="width: 45%" />
            </v-row>
            <v-row justify="start" class="label_name">환자 본인 여부</v-row>
            <v-row class="pt-1">
              <v-radio-group inline>
                <v-radio label="환자" value="0"></v-radio>
                <v-radio label="보호자" value="1"></v-radio>
              </v-radio-group>
            </v-row>
            <v-row justify="start" class="label_name">병명</v-row>
            <v-row class="pt-1 pb-2">
              <v-combobox
                v-model="chips"
                :items="cancerList"
                chips
                clearable
                multiple
                variant="solo"
              >
                <template v-slot:selection="{}">
                  <v-chip
                    v-bind="attrs"
                    :model-value="selected"
                    closable
                    @click="select"
                    @click:close="remove(item)"
                  >
                    <strong>{{ item }}</strong
                    >&nbsp;
                    <span>(interest)</span>
                  </v-chip>
                </template>
              </v-combobox>
            </v-row>
            <v-row justify="start" class="label_name">그룹 코드 (6자리)</v-row>
            <v-row class="pt-1 pb-2">
              <input class="text_input" placeholder="ABCDEF" />
            </v-row>
          </v-col>
          <v-col cols="12">
            <v-btn type="submit" block class="mt-2" elevation="0" color="primary">회원가입</v-btn>
          </v-col>
        </v-row>
      </v-form>
    </v-col>
  </v-container>
</template>

<script>
export default {
  data () {
      return {
        chips: [],
        cancerList: ['간암', '난소암', '대장암', '위암', '췌장암'],
      }
    },

    methods: {
      remove (item) {
        this.chips.splice(this.chips.indexOf(item), 1)
      },
    },
}
</script>

<style scoped>
.register_wrap {
  width: 400px;
}
.register_wrap > .v-col > .v-row {
  justify-content: center;
}
.label_name {
  font-size: 1rem;
}
.text_input {
  border: 1px solid grey;
  border-radius: 5px;
  width: 100%;
  padding: 10px;
}
.date_input {
  border: 1px solid grey;
  border-radius: 5px;
  width: 30%;
  padding: 10px;
}
</style>
