<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <div class="mt-4 px-4">
      <Input name="tata" type="text" label="First Name"></Input>
    </div>
    <div class="mt-4 px-4">
      <Input name="tata" type="text" label="Last Name" value="Sarfar"></Input>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import Input from "@/components/form/Input.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
    Input
  }
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
}
</style>
