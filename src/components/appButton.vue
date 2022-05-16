<template>
  <div class="hello">
  <!-- *** this button uses props *** -->

    <!-- <button>
    <icon v-if="showIcon" width="20" height="20"/>
    {{ text }}
    </button> -->
    <!-- <button v-on="$listeners">
      <slot></slot>
    </button> -->
  </div>
</template>

<script>

export default {
  name: 'appButton',
  components: {
  
  },
  props: [
    "text",
    "showIcon"
  ],
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
