<template>
  <form @submit.prevent="onSubmit">
    <textarea v-model="body" required placeholder="Type tweet here" />
    <button class="btnTweet btn" type="submit">Post tweet</button>
  </form>
</template>

<script>
  import {ref} from "vue"
  export default {
    setup(_, {emit}) {
      const body = ref('')

      const onSubmit = () => {
        emit('onSubmit', {
        id: Math.round(Math.random() * 30),
        avatar: `https://avatars.dicebear.com/api/human/${Date.now()}.svg`,
        body: body.value,
        likes: 0,
        date: new Date(Date.now()).toLocaleString(),
      })
      body.value = ''
      }
      return {body, onSubmit}
    }
  }
// export default {
//   data() {
//     return {
//       body: '',
//     }
//   },
//   methods: {
//     onSubmit() {
      // this.$emit('onSubmit', {
      //   id: Math.round(Math.random() * 30),
      //   avatar: `https://avatars.dicebear.com/api/human/${Date.now()}.svg`,
      //   body: this.body,
      //   likes: 0,
      //   date: new Date(Date.now()).toLocaleString(),
      // })
//       //rest
//       this.body = '';
//     },
//   },
// }
</script>
