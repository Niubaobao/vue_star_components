<template>
  <div class="star">
    <label class="star-star" :style="{fontSize:size+'px'}"
           v-for="item in items" :class="{'is-select': ((value>=item)&&value!==null)}"
           v-on:mouseover="star_over(item)"
           v-on:mouseout="star_out"
           v-on:click="set(item)"
    >★</label>
  </div>

</template>

<script>
  export default {
    name: 'star',
    props: {
      size: {
        type: Number,
        default: 50
      },
      disabled: {
        type: Boolean,
        default: false
      },
      max: {
        type: Number
      },
      scort: {
        type: Number,
        default: 0
      }
    },
    data () {
      return {
        value: this.scort
      }
    },
    methods: {
      star_over: function (index) {
        if (this.disabled) {
          return
        }
        this.temp_value = this.value
        this.value = index
      },
      star_out: function () {
        if (this.disabled) {
          return
        }
        this.value = this.temp_value
      },
      set: function (index) {
        if (this.disabled) {
          return
        }
        this.temp_value = index
        this.value = index
      }

    },
    computed: {
      items: function () {
        if (!this.max) {
          return [1, 2, 3, 4, 5]
        }
        var numberArray = []
        for (var i = 1; i <= this.max; i++) {
          numberArray.push(i)
        }
        return numberArray
      }
    }
  }

</script>

<style>
  .star {

  }

  .is-select {
    color: red;
  }


</style>
