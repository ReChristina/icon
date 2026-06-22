<template>
  <main
    class="min-h-screen bg-[#f4f7fb] px-[40px] py-[32px] font-['Inter','PingFang_SC','Microsoft_YaHei',sans-serif] text-[#111827]"
  >
    <section
      class="mx-auto flex min-h-[812px] w-full max-w-[1200px] overflow-hidden rounded-[32px] bg-white shadow-[0_24px_80px_rgba(15,23,42,0.12)]"
      aria-label="登录页"
    >
      <aside
        class="relative flex w-[560px] flex-col justify-between overflow-hidden bg-[#0f3d5e] px-[56px] py-[52px] text-white"
      >
        <div
          class="absolute left-[-116px] top-[-116px] h-[316px] w-[316px] rounded-full bg-[#48d6c4]/20 blur-[2px]"
        ></div>
        <div
          class="absolute bottom-[-144px] right-[-104px] h-[362px] w-[362px] rounded-full bg-[#78a7ff]/25 blur-[3px]"
        ></div>
        <div
          class="absolute left-[80px] top-[250px] h-[224px] w-[224px] rounded-full border border-white/20"
        ></div>

        <div class="relative z-10 flex items-center gap-[12px]">
          <div
            class="flex h-[44px] w-[44px] items-center justify-center rounded-[14px] bg-white/14 ring-1 ring-white/24"
          >
            <span class="h-[18px] w-[18px] rounded-[6px] bg-[#50e3c2]"></span>
          </div>
          <span class="text-[22px] font-semibold leading-[28px] tracking-[-0.2px]">BrandSpace</span>
        </div>

        <div class="relative z-10 mt-[96px]">
          <p class="text-[18px] font-medium leading-[28px] text-[#b8d9ea]">欢迎回来</p>
          <h1 class="mt-[18px] max-w-[408px] text-[48px] font-bold leading-[58px] tracking-[-1.5px]">
            开始管理你的数字工作空间
          </h1>
          <p class="mt-[24px] max-w-[400px] text-[17px] font-normal leading-[30px] text-[#d6e7ef]">
            登录后同步团队资料、项目进度与关键数据，让每一次协作都更高效。
          </p>
        </div>

        <div class="relative z-10 grid gap-[16px]">
          <article
            v-for="item in featureItems"
            :key="item.title"
            class="flex items-start gap-[14px] rounded-[20px] bg-white/[0.08] p-[18px] ring-1 ring-white/[0.12]"
          >
            <div
              class="mt-[2px] flex h-[34px] w-[34px] shrink-0 items-center justify-center rounded-[12px] bg-white/14 text-[16px] font-bold text-[#50e3c2]"
            >
              {{ item.index }}
            </div>
            <div>
              <h2 class="text-[16px] font-semibold leading-[22px]">{{ item.title }}</h2>
              <p class="mt-[4px] text-[14px] font-normal leading-[22px] text-[#c8dce7]">
                {{ item.description }}
              </p>
            </div>
          </article>
        </div>
      </aside>

      <section class="flex flex-1 items-center justify-center px-[72px] py-[56px]">
        <div class="w-full max-w-[440px]">
          <div class="mb-[48px]">
            <p class="text-[16px] font-medium leading-[24px] text-[#5f6b7a]">登录账户</p>
            <h2 class="mt-[10px] text-[40px] font-bold leading-[48px] tracking-[-1px] text-[#101828]">
              Welcome back
            </h2>
            <p class="mt-[14px] text-[16px] font-normal leading-[26px] text-[#667085]">
              请输入你的账号信息以继续访问控制台。
            </p>
          </div>

          <form class="grid gap-[22px]" @submit.prevent>
            <label v-for="field in formFields" :key="field.id" class="block">
              <span class="text-[14px] font-semibold leading-[20px] text-[#344054]">
                {{ field.label }}
              </span>
              <input
                :id="field.id"
                :type="field.type"
                :placeholder="field.placeholder"
                class="mt-[8px] h-[54px] w-full rounded-[14px] border border-[#d0d5dd] bg-white px-[18px] text-[16px] font-normal leading-[24px] text-[#101828] outline-none transition placeholder:text-[#98a2b3] focus:border-[#1e6b8f] focus:ring-[4px] focus:ring-[#d4edf6]"
              />
            </label>

            <div class="flex items-center justify-between pt-[2px]">
              <label class="flex items-center gap-[10px] text-[14px] font-medium leading-[20px] text-[#475467]">
                <input
                  type="checkbox"
                  class="h-[16px] w-[16px] rounded-[4px] border-[#d0d5dd] text-[#1e6b8f] focus:ring-[#1e6b8f]"
                />
                记住我
              </label>
              <a href="#" class="text-[14px] font-semibold leading-[20px] text-[#1e6b8f]">
                忘记密码？
              </a>
            </div>

            <button
              type="submit"
              class="mt-[8px] h-[56px] rounded-[16px] bg-[#1e6b8f] text-[16px] font-semibold leading-[24px] text-white shadow-[0_12px_24px_rgba(30,107,143,0.24)] transition hover:bg-[#175777] focus:outline-none focus:ring-[4px] focus:ring-[#d4edf6]"
            >
              登录
            </button>
          </form>

          <div class="my-[30px] flex items-center gap-[16px]">
            <span class="h-px flex-1 bg-[#eaecf0]"></span>
            <span class="text-[14px] font-medium leading-[20px] text-[#98a2b3]">或</span>
            <span class="h-px flex-1 bg-[#eaecf0]"></span>
          </div>

          <button
            type="button"
            class="flex h-[54px] w-full items-center justify-center gap-[12px] rounded-[14px] border border-[#d0d5dd] bg-white text-[16px] font-semibold leading-[24px] text-[#344054] transition hover:bg-[#f9fafb]"
          >
            <svg class="h-[22px] w-[22px]" viewBox="0 0 22 22" aria-hidden="true">
              <path
                fill="#4285f4"
                d="M21.56 11.25c0-.78-.07-1.53-.2-2.25H11v4.26h5.92c-.26 1.37-1.03 2.53-2.2 3.31v2.75h3.57c2.09-1.92 3.27-4.75 3.27-8.07Z"
              />
              <path
                fill="#34a853"
                d="M11 22c2.97 0 5.46-.98 7.28-2.67l-3.57-2.75c-.99.66-2.25 1.05-3.71 1.05-2.86 0-5.29-1.93-6.16-4.53H1.16v2.84A10.99 10.99 0 0 0 11 22Z"
              />
              <path
                fill="#fbbc05"
                d="M4.84 13.1A6.61 6.61 0 0 1 4.5 11c0-.73.12-1.44.34-2.1V6.06H1.16A10.99 10.99 0 0 0 0 11c0 1.77.42 3.45 1.16 4.94l3.68-2.84Z"
              />
              <path
                fill="#ea4335"
                d="M11 4.38c1.62 0 3.07.56 4.22 1.65l3.14-3.14C16.46 1.12 13.97 0 11 0A10.99 10.99 0 0 0 1.16 6.06L4.84 8.9C5.71 6.31 8.14 4.38 11 4.38Z"
              />
            </svg>
            使用 Google 登录
          </button>

          <p class="mt-[34px] text-center text-[15px] font-normal leading-[22px] text-[#667085]">
            还没有账号？
            <a href="#" class="font-semibold text-[#1e6b8f]">立即注册</a>
          </p>
        </div>
      </section>
    </section>
  </main>
</template>

<script setup>
const featureItems = [
  {
    index: '1',
    title: '安全访问',
    description: '统一认证保护你的团队数据与核心工作流。',
  },
  {
    index: '2',
    title: '快速协作',
    description: '登录后即可查看项目、任务和团队最新动态。',
  },
]

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
