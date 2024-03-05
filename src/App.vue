<script setup lang="ts">
import CustomInput from './components/CustomInput.vue';

// import { HOtpInput } from "@healerlab/vue3-simple-otp-input";

// const handleFinish = (otpCode: string) => {
//   // write logic with received code
// }

// const handleChange = (otpCode: string) => {
//   // write logic with changed code
// }

// ----------
</script>


<template>

<CustomInput />

<!-- <HOtpInput
  :length="6" 
  type="text" 
  @on-finish="handleFinish"
  @on-change="handleChange" 
  wrapperClassName="otp-input"
  :outlined="true"
  ref="otpInput"
  :only-number="true"
 
/> -->
</template>

<style scoped lang="scss">
.otp-input {
  :deep(input) {   
    outline: none;
    width: 40px;
    padding: 12px;
    font-size: 22px;
    border: none;
    margin-left: 10px;
    text-align: center;
    &:first-child {
      margin-left: 0;
    }
    &:focus {
      outline: none
    }
  }
}
</style>
