<template>
  <lable>이름: </lable>
  <input type="text" v-model="result.name" placeholder="이름" /><br />
  <lable>나이: </lable>
  <input type="number" v-model="result.age" placeholder="나이" /><br />
  <lable>성별: </lable>
  <lable>남성</lable>
  <input type="radio" name="gender" v-model="result.gender" value="male" /><br />
  <lable>여성</lable>
  <input 
    type="radio"
    name="gender"
    v-model="result.gender"
    value="female"
  /><br />
  <lable>취미: </lable>
  <span v-for="hobby in hobby_options" :key="hobby">
    <label>{{ hobby }}</label>
    <input type="checkbox" v-model="result.hobby" v-bind:value="hobby" />
  </span><br />
  <lable>비번: </lable>
  <input type="password" v-model="result.password" /><br />
  <lable>국가: </lable>
  <select v-model="result.country">
    <option v-for="country in country_options" :key="country">
      {{ country }}
    </option>
  </select><br />
  <lable>날짜: </lable>
  <input type="date" v-model="result.date" /><br />
  <lable>시간: </lable>
  <input type="time" v-model="result.time" /><br />
  <lable>색깔: </lable>
  <input type="color" v-model="result.color" /><br />
  <lable>범위: </lable>
  <input type="range" v-model="result.range" /><br />
  <div>
    <h3>결과</h3>
    <hr />
    {{ result }}
  </div>
</template>

<script>
import { reactive } from 'vue'

export default {
  setup() {
    const name = ''
    const age = 0
    const gender = 'male'
    const hobby = ['스포츠']
    const password = ''
    const country = '한국'
    const date = '2023-03-02'
    const time = '15:21'
    const color = '#541717'
    const range = '64'
    const country_options = ['한국', '미국', '중국']
    const hobby_options = ['스포츠', '그림', '음악', '코딩']

    const result = reactive({
      name,
      age,
      gender,
      hobby,
      password,
      country,
      date,
      time,
      color,
      range
    })

    return {
      result,
      country_options,
      hobby_options
    }
  }
}
</script>