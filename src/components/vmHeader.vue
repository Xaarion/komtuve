<template>
  <div class="card-header">
    <form class="form-inline">
      <div class="form-group mb-2">
        <label for="inputNumberOfVM">Machines Virtuelles</label>
      </div>
      <div class="form-group mx-sm-3 mb-2">
        <input type="number" class="form-control" id="inputNumberOfVM" placeholder="Nombre de VM" v-model="wantedNbVm" />
      </div>
    </form>
    <div class="card-body">
      <div class="card-columns">
        <div v-bind:key="i" v-for="i in dataStore.data.sequence.length">
          <virtualMachinaVue v-bind:nombredevm="i"></virtualMachinaVue>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import virtualMachinaVue from "./virtualMachina.vue";
import { store } from "../store.js";

export default {
  name: "vmHeader",
  components: {
    virtualMachinaVue,
  },

  data() {
    return {
      dataStore: store,
      wantedNbVm: 0
    };
  },
  watch: {
    wantedNbVm () {
      this.changeVM()
      
    }
  },
  methods: {
    changeVM () {

      for (let i = 0; i < 9; i++) {
  str = str + i;


      this.dataStore.data.sequence.push(
        {
          memoire: '',
          id: this.dataStore.data.sequence.length
        }
      )
      }

    }
  },


};
</script>


