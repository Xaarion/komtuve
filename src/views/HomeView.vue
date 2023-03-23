<template>
  <div class="home">
    <div class="contailer-fluid">

      <GlobalConfig />
      <div class="card mt-3">
        <vmHeader />
        <virtualMachina />  
      </div>  
    </div>
  </div>
</template>

<script>
// @ is an alias to /src




import GlobalConfig from '@/components/GlobalConfig.vue'
import vmHeader from '@/components/vmHeader.vue'
import virtualMachina from '@/components/virtualMachina.vue'


export default {
  name: 'HomeView',
  components: {
    GlobalConfig,
    vmHeader,
    virtualMachina
  }
}
</script>
