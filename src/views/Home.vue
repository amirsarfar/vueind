<template>
  <div class="home">
    <div class="mt-4 px-4">
      <Input
        name="tata"
        type="text"
        label="First Name"
        pattern="n+"
        required
      ></Input>
    </div>
    <div class="mt-4 px-4">
      <Input name="tata" type="text" label="Last Name" value="Sarfar"></Input>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Input from "@/components/form/Input.vue";

export default {
  name: "Home",
  components: {
    Input
  }
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
}
</style>
