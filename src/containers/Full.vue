<template>
  <div class="app">
    <AppHeader/>
    <div class="app-body">
      <Sidebar :nav-items="nav"/>
      <main class="main">
        <breadcrumb :list="list"/>
        <div class="container-fluid">
          <router-view/>
        </div>
      </main>
      <AppAside/>
    </div>
    <AppFooter/>
  </div>
</template>

<script>
import nav from '../_nav';
import {
  Header as AppHeader,
  Sidebar,
  Aside as AppAside,
  Footer as AppFooter,
  Breadcrumb
} from '../components/';

export default {
  name: 'Full',
  components: {
    AppHeader: AppHeader,
    Sidebar: Sidebar,
    AppAside: AppAside,
    AppFooter: AppFooter,
    Breadcrumb: Breadcrumb
  },
  data: () => {
    return { nav: nav.items };
  },
  computed: {
    name() {
      return this.$route.name;
    },
    list() {
      return this.$route.matched;
    }
  }
};
</script>
