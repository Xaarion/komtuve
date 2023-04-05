<template>
  <div class="card-header">
    <form class="form-inline">
      <div class="form-group mb-2">
        <label for="inputNumberOfVM">Machines Virtuelles</label>
      </div>
      <div class="form-group mx-sm-3 mb-2">
        <input
          type="number"
          class="form-control"
          id="inputNumberOfVM"
          placeholder="Nombre de VM"
          v-model="wantedNbVm"
        />
      </div>
    </form>
    <div class="card-body">
      <div class="card-columns">
        <div
          v-for="i in dataStore.data.sequence"
          :key="dataStore.data.sequence[i]"
        >
          <virtualMachinaVue v-bind:nombredelavm="i.id"></virtualMachinaVue>
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
      wantedNbVm: 0,
    };
  },

  mounted() {
    this.wantedNbVm = this.dataStore.data.nbrVm;
    console.log(this.wantedNbVm);
  },


  watch: {
    wantedNbVm() {
      this.changeVM();
      this.dataStore.data.nbrVm = this.wantedNbVm;
    },
  },
  
  methods: {
    changeVM() {
      this.dataStore.data.sequence = [];

      for (let i = 0; i < this.wantedNbVm; i++) {
        this.dataStore.data.sequence.push({
          memoire: "",
          id: this.dataStore.data.sequence.length,

        });
        console.log(this.dataStore.data.sequence.length)
      }
    },
  },
};
</script>


