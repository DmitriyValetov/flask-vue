<template>
  <div class="container">
    <button type="button" class="btn btn-primary">{{ msg }}</button>
  </div>
</template>

<script>

import axious from 'axios';

export default {
  name: 'Ping',
  data() {
    return {
      msg: 'Hello!',
    };
  },
  methods: {
    getMessage() {
      const path = 'http://localhost:5000/ping';
      axious.get(path)
        .then((res) => {
          this.msg = res.data;
        })
        .catch((error) => {
          // eslint-disable-next-line
          console.error(error);
        });
    },
  },
  created() {
    this.getMessage();
  },
};
</script>
