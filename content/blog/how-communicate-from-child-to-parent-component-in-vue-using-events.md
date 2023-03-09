---
path: how-comunicate-from-child-to-parent-component-vue-using-events
date: 2023-02-21T10:22:00.841Z
title: How communicate from child to parent component in Vue using events
---
S﻿ometimes we need to pass data from child component to parent component in Vue, in this article we will understant how to do it.

T﻿here are a lot of option to do this but we will this using events.

P﻿arent component:

```
<template>
  <userData @saveUserData="user => receiveUserData(user)" />
</template>

<script>
  export default {
    methods: {
      receiveUserData(user) {
        console.log('user data', user)
      }
    }
  }
</script>


```

C﻿hild component **UserData:**

```
<template>
  <form>
    <input v-model="name" />
    <input v-model="age" />
    <input v-model="phone" />
    
    <button @click="handleEmitEvent">Save</button>
  </form>
</template>

<script>
  export default {
    data() {
      user: {
        name: '',
        age: null,
        phone: ''
      }
    },
    methods: {
      handleEmitEvent() {
        this.$emit('saveUserData', this.user)
      }
    }
  }
</script>
```