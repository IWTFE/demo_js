<template>
<div class='hello '>
  <button @click='test'>发送请求</button>
</div>
</template>

<script>
import rest from 'src/js/security/rest_model'
export default {
  name: 'hello',
  data() {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    test() {
      var userId = '02 '
      var loginPwd = '666 '
      var shortSinglePhone = '02 '
      var crmCorpInfoOid = '312312312gregre312312312312312 '

      rest.post('http://192.168.88.56/user/login.do ', {
        'body ': {
          'userId ': userId,
          'loginPwd ': loginPwd,
          'shortSinglePhone ': shortSinglePhone,
          'crmCorpInfoOid ': crmCorpInfoOid
        },
        'businessId ': 'CC_CRM_LOGIN '
      }, function(res, code) {
        console.log(res)
      }, function(res) {
        alert('网络连接问题，请稍后重试！ ')
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
