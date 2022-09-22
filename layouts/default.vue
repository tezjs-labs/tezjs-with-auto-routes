<script>
import headerComponent from "/@/components/header.vue";
import footerComponent from "/@/components/footer.vue";

export default {
    components: {
    headerComponent: headerComponent,
    footerComponent:footerComponent
  },
}
</script>
<template>
    <headerComponent></headerComponent>
        <tez-slot></tez-slot>
    <footerComponent></footerComponent>
</template>
