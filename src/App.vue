<template>
  <div>
   <appHeader />
    <router-view> </router-view>
  </div>
</template>
<script>
import appHeader from '@/components/appHeader';
import axios from "axios";
export default {
    components : {
        appHeader,
    }
};
</script>