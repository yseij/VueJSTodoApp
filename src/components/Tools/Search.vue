<template>
  <v-text-field
    v-model="search"
    @focus="searchClosed = false"
    @blur="searchClosed = true"
    :class="{ closed: searchClosed && !search }"
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
      search: null,
      searchClosed: true,
    };
  },
};
</script>

<style lang="sass">
.expanding-search
  transition: max-width 0.3s
  .v-input__slot
    cursor: pointer !important
    &:before, &after
      border-color: transparant !important
  &.closed
    max-width: 45px
    .v-input__slot
      background: rgb(0,0,0, 0) !important
</style>
