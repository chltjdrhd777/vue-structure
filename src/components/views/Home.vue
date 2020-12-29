<template>
  <div>
    <h1>Welcom home {{ title }}</h1>
    <input type="text" v-model="inputV" />
    <input
      type="text"
      placeholder="testInput"
      v-model="inputValue"
      @change="detectChange"
    />
    <button type="button" @click="getData">
      Get
    </button>
    <button type="button" @click="setData">set</button>

    //! if I want to use "toggle", v-show is good, but if want to set
    conditional thing, v-if is great
    <table class="table table-bordered" v-show="tableshow">
      <tr v-for="data in arrayData" :key="data.d">
        <td>{{ data.d }}</td>
        <td>{{ data.t }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "Home",

  data() {
    return {
      title: "test1",
      title2: "test2",
      inputV: "this is input values",
      inputValue: "",
      arrayData: [
        { d: "1", t: "t1" },
        { d: "2", t: "t2" },
        { d: "3", t: "t3" },
      ],
      tableshow: false,
    };
  },

  methods: {
    getData() {
      alert(this.inputValue);
    },
    setData() {
      this.tableshow = !this.tableshow;
    },
    detectChange() {
      console.log("change is coming!");
    },
  },

  watch: {
    inputValue() {
      console.log(`input value is changed : ${this.inputValue}`);
    },
  },

  /* beforeCreate() {
    console.log("beforeCreate");
  },

  created() {
    console.log("created");
  },

  beforeMount() {
    console.log("beforeMount");
  },

  mounted() {
    console.log("mounted");
  },

  beforeUpdate() {
    console.log("beforeUpdate");
  },

  updated() {
    console.log("updated");
  },

  beforeDestroy() {
    console.log("beforeDestroy");
  },

  destroyed() {
    console.log("destroyed");
  }, */
};
</script>

<style></style>
