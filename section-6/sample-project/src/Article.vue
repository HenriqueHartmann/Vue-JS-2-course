<template>
  <div class="article">
    <h1>{{ title }}</h1>

    <p>Published on {{ published | moment }}</p>
    <p>Shares: {{ shares }}</p>
    <p class="lead">{{ content }}</p>
    <app-author :author="author"></app-author>

    <br>
    <app-social-sharing :article="$data" @articleWasShared="shared"></app-social-sharing>
  </div>
</template>

<script>
  import moment from 'moment'
  import Author from './Author.vue'
  import Social from './Social.vue'

  export default {
    data () {
      return {
        title: '10 Reasons Why Vue.JS is Awesome',
        published: new Date(),
        content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
        author: {
          firstName: 'Henrique',
          lastName: 'Hartmann'
        },
        shares: 0
      }
    },
    methods: {
      shared: function (event) {
        this.shares++
        console.log(event)
      }
    },
    filters: {
      moment: function (value) {
        return moment(value).format('MMMM Do')
      }
    },
    components: {
      'appAuthor': Author,
      'appSocialSharing': Social
    }
  }
</script>
