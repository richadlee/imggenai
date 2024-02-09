<template>
  <q-page class="flex-center bg-black">
    <div class="column items-center" >
      <div class="col text-white q-mt-md">
        <img src="~assets/logoname.webp" height="70px"/>
      </div>
      <div class="col text-white q-mb-md">
        <div class="q-px-lg text-h4 text-weight-bolder " width="380px">
          Start your MAGICAL DRESSING journey
        </div>
      </div>
      <div class="col text-white q-mb-md">
        <div class="q-px-md text-h7 text-overline" width="380px">
          Try our bot for the most natural effects.
        </div>
      </div>
      <div class="col text-white q-mb-md">
        <q-btn icon="send" size="18px" color="primary" label="Try It Now" :href="tryItNowLink"/>
      </div>
      <div class="q-pa-md row q-col-gutter-md">
        <div class="col-12 col-md-4" :key="n">
          <img src="https://i.postimg.cc/Bnz9jYsW/0.png" width="100%"/>
        </div>
        <div class="col-12 col-md-4" :key="n">
          <img src="https://i.postimg.cc/9Q0HF36t/1.png" width="100%"/>
        </div>
        <div class="col-12 col-md-4" :key="n">
          <img src="https://i.postimg.cc/50ch3X6n/2.png" width="100%"/>
        </div>
      </div>
      <div class="q-pa-md row q-col-gutter-md">
        <div class="col-12 col-md-4" :key="n">
          <img src="https://i.postimg.cc/85hqnTvD/3.png" width="100%"/>
        </div>
        <div class="col-12 col-md-4" :key="n">
          <img src="https://i.postimg.cc/3NYzszjG/4.png" width="100%"/>
        </div>
        <div class="col-12 col-md-4" :key="n">
          <img src="https://i.postimg.cc/jjJVPHdD/5.png" width="100%"/>
        </div>
      </div>

      <div class="col text-white q-mb-md">
        <q-btn icon="send" size="18px" color="primary" label="Try It Now" :href="tryItNowLink"/>
      </div>
      <div class="col text-white">
        <div class="q-pa-md" width="380px" >
          <q-card class="my-card bg-grey-9" flat bordered width="380px">
            <q-card-section horizontal>
              <q-card-section>
                <div class="text-h4 q-py-md">🔐</div>
              </q-card-section>

              <q-card-section>
                <div class="text-h6">It’s completely safe.</div>
                <div class="text-h8">ImgGenAI is highly secure and discrete. Your actions are not published anywhere.</div>
              </q-card-section>
            </q-card-section>
        </q-card>
        </div>
      </div>
      <div class="col text-white">
        <div class="q-pa-md" width="380px" >
          <q-card class="my-card bg-grey-9" flat bordered width="380px">
            <q-card-section horizontal>
              <q-card-section>
                <div class="text-h4 q-py-md">💪</div>
              </q-card-section>

              <q-card-section>
                <div class="text-h6">Multiple dressing effects</div>
                <div class="text-h8">Also provide various dressing effects such as schooluniform, dress, formal, swimsuit etc</div>
              </q-card-section>
            </q-card-section>
        </q-card>
        </div>
      </div>
      <div class="col text-white">
        <div class="q-pa-md" width="380px" >
          <q-card class="my-card bg-grey-9" flat bordered width="380px">
            <q-card-section horizontal>
              <q-card-section>
                <div class="text-h4 q-py-md">🔥</div>
              </q-card-section>

              <q-card-section>
                <div class="text-h6">Constantly updated AI models</div>
                <div class="text-h8">Continuously updated AI models keep you at the forefront of technological advancements, helping you create high-quality artistic works.</div>
              </q-card-section>
            </q-card-section>
        </q-card>
        </div>
      </div>
      <div class="col text-white">
        <div class="q-pa-md" width="380px" >
          <q-card class="my-card bg-grey-9" flat bordered width="380px">
            <q-card-section horizontal>
              <q-card-section>
                <div class="text-h4 q-py-md">⚡</div>
              </q-card-section>

              <q-card-section>
                <div class="text-h6">Simple and fast</div>
                <div class="text-h8">With just a single click, you can bring your imagination to life, experiencing simplicity and speed.</div>
              </q-card-section>
            </q-card-section>
        </q-card>
        </div>
      </div>
      <div class="col text-white">
        <div class="q-pa-md" width="380px" >
          <q-card class="my-card bg-grey-9" flat bordered width="380px">
            <q-card-section horizontal>
              <q-card-section>
                <div class="text-h4 q-py-md">💵</div>
              </q-card-section>

              <q-card-section>
                <div class="text-h6">Earn money</div>
                <div class="text-h8">You can earn a 30% commission on user recharge through promotion</div>
              </q-card-section>
            </q-card-section>
        </q-card>
        </div>
      </div>
      <div class="col text-white" font="Arial">
        ©Copyright 2024 ImgGenAI imggenai@gmail.com
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent, ref, onMounted, watch } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  setup () {
    const refParam = ref('');
    // 组件挂载后获取URL参数
    onMounted(() => {
      const queryParams = new URLSearchParams(window.location.search);
      const refValue = queryParams.get('ref'); // 获取ref参数的值
      if (refValue) {
        refParam.value = refValue; // 如果有ref参数，则更新refParam的值
      }else{
        refParam.value = 'REFNET'
      }
    });
    // 动态生成"Try It Now"按钮的链接
    const tryItNowLink = ref('https://t.me/ImgGenAI_Bot?start=');
    watch(refParam, (newValue) => {
      tryItNowLink.value = `https://t.me/ImgGenAI_Bot?start=${newValue}`;
    }, { immediate: true });
    return {
      lorem: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
      slide: ref(1),
      tryItNowLink 
    }
  }
})
</script>
<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 380px
</style>