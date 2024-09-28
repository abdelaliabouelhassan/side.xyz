<template>
  <div class="bg-[#32D1C3] relative">
    <img src="/background.svg" class="w-full object-cover h-screen" alt="" />
    <div class="absolute top-0 left-0 w-full">
      <div class="w-full px-4 py-8 max-w-[1340px] mx-auto space-y-8">
        <div class="flex items-center gap-4">
          <div class="w-10 h-10 rounded-full bg-[#A5A5A5]">
            <img src="/logo.svg" class="w-full h-full object-cover" alt="" />
          </div>
          <div>
            <Select
              v-model="gg"
              :options="[
                {
                  name: 'Project 1',
                  value: 'project_1',
                },
                {
                  name: 'Project 2',
                  value: 'project_2',
                },
                {
                  name: 'Project 3',
                  value: 'project_3',
                },
              ]"
            />
          </div>
        </div>

        <div
          class="w-full max-w-[689px] rounded-[20px] bg-white mx-auto p-[16px] sm:p-[32px]"
          style="box-shadow: 8px 8px 0px 0px #001827"
        >
          <div class="space-y-3">
            <p
              class="text-[#001827] text-[20px] md:text-[32px] font-normal text-center"
            >
              Tweet about <span class="font-bold">@ProjectName</span> & <br />
              Earn <span class="font-bold">$ProjectToken</span> everyday!
            </p>

            <p class="text-[#001827] text-[13px] font-normal text-center">
              Safely connect your Twitter account and you wallet. Tweet using
              <span class="font-bold">@projectname</span> and earn airdrops
            </p>
          </div>

          <div class="w-full flex justify-center items-center gap-4 py-6">
            <button
              class="flex items-center text-xs sm:text-base gap-2 text-white font-bold px-3 sm:px-5 py-3 bg-[#21A4F3] rounded-lg hover:scale-105 duration-150"
              style="box-shadow: 4px 4px 0px 0px #1882c1"
            >
              <svg
                width="17"
                height="17"
                viewBox="0 0 17 17"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M16.4883 16.3125L10.2404 7.20596L10.2511 7.21449L15.8845 0.6875H14.0019L9.41285 6L5.76855 0.6875H0.831387L6.66436 9.18965L6.66365 9.18893L0.511719 16.3125H2.39424L7.49623 10.402L11.5511 16.3125H16.4883ZM5.02266 2.10795L13.7888 14.8921H12.297L3.52377 2.10795H5.02266Z"
                  fill="white"
                />
              </svg>
              <span>Connect Twitter</span>
            </button>
            <button
              class="flex items-center text-xs sm:text-base gap-2 text-white font-bold px-3 sm:px-5 py-3 bg-[#FF3366] rounded-lg hover:scale-105 duration-150"
              style="box-shadow: 4px 4px 0px 0px #bc1f47"
            >
              <svg
                width="17"
                height="15"
                viewBox="0 0 17 15"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M2.66667 2.70833C2.05888 2.70833 1.47598 2.94977 1.04621 3.37954C0.616443 3.80931 0.375 4.39221 0.375 4.99999V12.5C0.375 13.1078 0.616443 13.6907 1.04621 14.1204C1.47598 14.5502 2.05888 14.7917 2.66667 14.7917H14.3333C14.9411 14.7917 15.524 14.5502 15.9538 14.1204C16.3836 13.6907 16.625 13.1078 16.625 12.5V4.99999C16.625 4.39221 16.3836 3.80931 15.9538 3.37954C15.524 2.94977 14.9411 2.70833 14.3333 2.70833H2.66667ZM12.25 7.70833C11.9737 7.70833 11.7088 7.81807 11.5134 8.01343C11.3181 8.20878 11.2083 8.47373 11.2083 8.74999C11.2083 9.02626 11.3181 9.29121 11.5134 9.48656C11.7088 9.68191 11.9737 9.79166 12.25 9.79166C12.5263 9.79166 12.7912 9.68191 12.9866 9.48656C13.1819 9.29121 13.2917 9.02626 13.2917 8.74999C13.2917 8.47373 13.1819 8.20878 12.9866 8.01343C12.7912 7.81807 12.5263 7.70833 12.25 7.70833Z"
                  fill="white"
                />
                <path
                  d="M12.2375 0.0575C12.4842 -0.0082513 12.7428 -0.0164311 12.9932 0.0335918C13.2436 0.0836146 13.4791 0.190503 13.6817 0.346006C13.8842 0.501509 14.0483 0.701469 14.1613 0.930454C14.2743 1.15944 14.3331 1.41132 14.3333 1.66667H6L12.2375 0.0575Z"
                  fill="white"
                />
              </svg>

              <span>Connect Wallet</span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import Select from "./components/select.vue";
const gg = ref("project_2");
</script>
