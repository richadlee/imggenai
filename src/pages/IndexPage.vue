<template>
  <q-page class="flex-center bg-black">
    <div class="column items-center" >
      <div class="col text-white q-mt-md">
        <img src="~assets/logoname.webp" height="70px"/>
      </div>
      <div class="col text-white q-mb-md">
        <div class="q-px-lg text-h4 text-weight-bolder " width="380px">
          Undress ANYONE
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
          <img src="~assets/0_0.webp" width="100%"/>
        </div>
        <div class="col-12 col-md-4" :key="n">
          <img src="~assets/1_1.webp" width="100%"/>
        </div>
        <div class="col-12 col-md-4" :key="n">
          <img src="~assets/2_2.webp" width="100%"/>
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
                <div class="text-h8">Undress AI is highly secure and discrete. Your actions are not published anywhere.</div>
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
                <div class="text-h8">Also provide various dressing effects such as bundling, semen, bikini, bunnysuit, facial, rolling eyes and tongue out, etc</div>
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
                <div class="text-h6">The latest outpainting effects</div>
                <div class="text-h8">The latest outpainting effects such as blowjob, titfxck, handjob, and milking are also very popular</div>
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
                <div class="text-h4 q-py-md">⚙</div>
              </q-card-section>

              <q-card-section>
                <div class="text-h6">Preference Settings</div>
                <div class="text-h8">You can customize breasts size and private parts</div>
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
        braundress@gmail.com
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
    const tryItNowLink = ref('https://t.me/BraUndress_Entry_Bot?start=');
    watch(refParam, (newValue) => {
      tryItNowLink.value = `https://t.me/BraUndress_Entry_Bot?start=${newValue}`;
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