<template>
  <ContTitle title="scientist" />
  <PortCont />
</template>

<script>
// @ is an alias to /src

import ContTitle from "@/components/layout/ContTitle.vue";
import PortCont from "@/components/port/PortCont.vue";

export default {
  components: {
    ContTitle,
    PortCont,
  },
};
</script>
