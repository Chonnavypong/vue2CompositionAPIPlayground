<template>
  <div>
    <p>Basic Computed Playground</p>
    <input type="checkbox" v-model="statusBasic" value="a" /> {{ isCheck }} :
    {{ message }}
    <p>{{ statusBasic }}</p>
    <hr />
    <input type="checkbox" v-model="status" value="status" /> {{ isCheck }} :
    {{ message }}
    <p>{{ status }}</p>
    <hr />
    <input type="checkbox" v-model="b" value="b" /> 
    a: {{ a }} , b : {{ b }}
  </div>
</template>
<script>
export default {
  name: "computedPlayground",
  data() {
    return {
      a: 1,
      isCheck: false,
      message: "On Loaded",
      messageStatus: "Message of Status",
    };
  },
  computed: {
    status: {
      get: function() {
        return this.messageStatus;
      },
      set: function(val) {
        console.log(val);
        this.isCheck = val;
        this.isCheck
          ? (this.messageStatus = "Checked")
          : (this.messageStatus = "Uncheck");
      },
    },
    statusBasic: function() {
      console.log(this.isCheck);
      return this.isCheck;
    },
    b: {
      // getter
      get: function() {
        return this.a + 1;
      },
      // setter
      set: function(val) {
        console.log(val);
        this.isCheck ? (this.a = val - 1) : (this.a = val * 10);
      },
    },
  },
};
</script>
