<template>
  <v-text-field
    @focus="searchClosed = false"
    @blur="searchClosed = true"
    :class="{ closed: searchClosed }"
    class="expanding-search mt-1"
    placeholder="Search"
    filled
    dense
    clearable
    prepend-inner-icon="mdi-magnify"
  ></v-text-field>
</template>

<script>
export default {
  data() {
    return {
      searchClosed: true,
    };
  },
};
</script>

<style lang="sass">
.expanding-search
  transition: max-width 0.3s
  .v-input__slot
    &:before, &after
      border-color: transparant !important
  &.closed
    max-width: 45px
    .v-input__slot
      background: rgb(0,0,0, 0) !important
</style>
