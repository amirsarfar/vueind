<template>
  <div class="input-control">
    <label :for="name" :class="labelClasses">{{ label }}</label>
    <input
      :class="inputClasses"
      :type="type"
      :name="name"
      @focus="inputFocused"
      @blur="inputBlured"
      @keyup="inputChanged"
      v-model="val"
    />
  </div>
</template>

<script>
export default {
  name: "Input",
  props: {
    name: String,
    label: String,
    type: String,
    value: String,
    pattern: String,
    required: Boolean
  },
  data() {
    return {
      focused: false,
      val: this.value ? this.value : "",
      isValid: true,
      isTouched: false
    };
  },
  computed: {
    labelClasses() {
      return {
        "hover-label": this.focused || this.val.trim() != ""
      };
    },
    inputClasses() {
      return [
        "rounded border-gray-300 border focus:outline-none focus:ring focus:border-gray-50 focus:ring-blue-200",
        this.isValid ? "ring-green-300" : "ring-red-300",
        this.shouldShowRing ? "ring" : ""
      ];
    },
    shouldShowRing() {
      return (
        this.pattern != undefined &&
        this.pattern != "" &&
        (this.required || this.val.trim() != "") &&
        this.isTouched
      );
    }
  },
  methods: {
    inputFocused() {
      this.focused = true;
    },
    inputBlured() {
      this.focused = false;
    },
    inputChanged() {
      this.isTouched = true;
      var re = new RegExp(this.pattern, "i");
      if (re.test(this.val)) {
        this.isValid = true;
        return;
      }
      this.isValid = false;
    }
  }
};
</script>

<style lang="scss">
.input-control {
  position: relative;
  label {
    position: absolute;
    top: 50%;
    left: 1rem;
    transform: translateY(-50%);
    font-size: 1.25rem;
    transition: all 0.3s;
    color: gray;
    &.hover-label {
      color: gray;
      top: 25%;
      font-size: 0.85rem;
    }
  }
  input {
    width: 100%;
    height: 3rem;
    padding-left: 1rem;
    padding-top: 1rem;
    font-size: 1.25rem;
    font-weight: 400;
  }
}
</style>
