<template>
  <div class="">
    <nav-menu :menus="menus" :collapse="collapse"></nav-menu>
    <div class="collapse-button">
      <i :class="`el-icon-s-${collapse ? 'unfold' : 'fold'}`" @click="toggleCollapse"></i>
    </div>
  </div>
</template>

<script>
import { createNamespacedHelpers } from 'vuex'
import NavMenu from '../components/NavMenu'
const { mapState, mapActions } = createNamespacedHelpers('common')
export default {
  name: 'GlobalAside',
  computed: {
    ...mapState({
      collapse: 'collapse',
      menus: 'menus'
    })
  },
  methods: {
    ...mapActions(['toggleCollapse'])
  },
  components: { NavMenu }
}
</script>

<style scoped lang="scss">
.collapse-button {
  height: 56px;
  background-color: $--bg-color-container;
  border-right: $--border-basic;
  text-align: right;
  i {
    font-size: $--font-size-title;
    height: 56px;
    width: 64px;
    line-height: 56px;
    text-align: center;
    margin-left: auto;
    color: $--color-info;
    &:hover {
      cursor: pointer;
      background: rgba(0, 0, 0, 0.1);
    }
  }
}
</style>
