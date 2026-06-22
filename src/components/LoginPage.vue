<template>
  <main
    class="relative min-h-screen overflow-hidden bg-[#f8fdff] font-['Inter','PingFang_SC','Microsoft_YaHei',sans-serif] text-[#1d2939]"
  >
    <img
      :src="loginBackground"
      alt=""
      class="pointer-events-none absolute inset-0 h-full w-full object-cover object-left"
    />

    <section class="relative z-10 flex min-h-screen items-center justify-end px-[88px] py-[48px]" aria-label="登录页">
      <section
        class="w-[406px] rounded-[24px] bg-white/80 px-[40px] py-[42px] shadow-[0_24px_70px_rgba(31,91,180,0.14)] ring-1 ring-[#d7e9ff]/70 backdrop-blur-[10px]"
      >
        <div class="mb-[38px]">
          <div class="flex items-center gap-[10px]">
            <span class="h-[30px] w-[30px] rounded-[10px] bg-gradient-to-br from-[#0a6cff] to-[#39d9e8] shadow-[0_8px_18px_rgba(10,108,255,0.26)]"></span>
            <span class="text-[20px] font-semibold leading-[28px] tracking-[-0.3px] text-[#1456c8]">数智城市</span>
          </div>
          <h1 class="mt-[32px] text-[32px] font-semibold leading-[40px] tracking-[-0.8px] text-[#101828]">
            欢迎登录
          </h1>
          <p class="mt-[10px] text-[15px] font-normal leading-[24px] text-[#667085]">
            请输入账号和密码进入管理平台
          </p>
        </div>

        <form class="grid gap-[20px]" @submit.prevent>
          <label v-for="field in formFields" :key="field.id" class="block">
            <span class="text-[14px] font-medium leading-[20px] text-[#344054]">
              {{ field.label }}
            </span>
            <input
              :id="field.id"
              :type="field.type"
              :placeholder="field.placeholder"
                class="mt-[8px] h-[48px] w-full rounded-[10px] border border-[#d6e4f7] bg-white/[0.92] px-[16px] text-[15px] font-normal leading-[22px] text-[#101828] outline-none transition placeholder:text-[#98a2b3] focus:border-[#287cff] focus:ring-[4px] focus:ring-[#dbeaff]"
            />
          </label>

          <div class="flex items-center justify-between pt-[2px]">
            <label class="flex items-center gap-[8px] text-[14px] font-normal leading-[20px] text-[#667085]">
              <input
                type="checkbox"
                class="h-[15px] w-[15px] rounded-[4px] border-[#bdd4f1] text-[#287cff] focus:ring-[#287cff]"
              />
              记住密码
            </label>
            <a href="#" class="text-[14px] font-medium leading-[20px] text-[#287cff]">
              忘记密码？
            </a>
          </div>

          <button
            type="submit"
            class="mt-[8px] h-[48px] rounded-[10px] bg-[#287cff] text-[16px] font-medium leading-[24px] text-white shadow-[0_12px_26px_rgba(40,124,255,0.28)] transition hover:bg-[#176cea] focus:outline-none focus:ring-[4px] focus:ring-[#dbeaff]"
          >
            登录
          </button>
        </form>

        <p class="mt-[28px] text-center text-[14px] font-normal leading-[22px] text-[#667085]">
          还没有账号？
          <a href="#" class="font-medium text-[#287cff]">立即注册</a>
        </p>
      </section>
    </section>
  </main>
</template>

<script setup>
import loginBackground from '../assets/images/login-city-background.svg'

const formFields = [
  {
    id: 'email',
    label: '邮箱地址',
    type: 'email',
    placeholder: '请输入邮箱地址',
  },
  {
    id: 'password',
    label: '密码',
    type: 'password',
    placeholder: '请输入密码',
  },
]
</script>

<style></style>
