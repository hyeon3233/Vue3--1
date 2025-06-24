<script setup>
import { reactive } from 'vue';
import { HttpService } from '@/services/HttpService';
import { useRouter } from 'vue-router';

const httpService = new HttpService();

const router = useRouter();

const state = reactive({
  memo: {
    title: '',
    content: '',
  },
});

const subimt = () => {
  httpService.addItem(state.memo);
  alert('저장했습니다.');
  router.push({ path: '/' });
};
</script>

<template>
  <h1>From.vue</h1>
</template>

<style scoped></style>
