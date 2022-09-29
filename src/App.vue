<template>
  <div class="wrapper">
    <!-- header -->
    <div class="wrapper-content">
      <div class="view">
        <div class="container">
          <Form @onSubmit="handleSubmit" />
          <List :items="items" />
        </div>
      </div>
    </div>
    <!-- footer -->
  </div>
</template>

<script>
import {ref} from 'vue'
import Form from '@/components/Form.vue'
import List from '@/components/List.vue'

export default {
  components: { Form, List },
  setup() {
    const items = ref ([
      {
        id: 1,
        avatar: `https://avatars.dicebear.com/api/human/1.svg`,
        body: 'hellow vue 3',
        likes: 12,
        date: new Date(Date.now()).toLocaleString(),
      },
      {
        id: 2,
        avatar: `https://avatars.dicebear.com/api/human/2.svg`,
        body: 'hellow batman',
        likes: 6,
        date: new Date(Date.now()).toLocaleString(),
      },
    ])
    const handleSubmit = item => items.value.push(item)
    // function handleSubmit(item) {
    //   items.value.push(item)
    // }

    return {
      items,
      handleSubmit
    }
  }
}

// export default {
//   components: { Form, List, },
//   data() {
//     return {
//       items: [
        // {
        //   id: 1,
        //   avatar: `https://avatars.dicebear.com/api/human/1.svg`,
        //   body: 'hellow vue 3',
        //   likes: 12,
        //   date: new Date(Date.now()).toLocaleString(),
        // },
        // {
        //   id: 2,
        //   avatar: `https://avatars.dicebear.com/api/human/2.svg`,
        //   body: 'hellow batman',
        //   likes: 6,
        //   date: new Date(Date.now()).toLocaleString(),
        // },
//       ],
//     };
//   },
//   methods: {
    // handleSubmit(item) {
    //   this.items.push(item)
    // }
//   }
// }
</script>
