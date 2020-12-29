<template>
  <div class="container">
  </div>
</template>

<script>
export default {
  middleware: 'auth',

  metaInfo () {
    return { title: this.$t('home') }
  },

  data () {
    return {
      formValidate: {
          name: '',
          mail: '',
          city: '',
          gender: '',
          interest: [],
          date: '',
          time: '',
          desc: ''
      },
    }
  },
  methods: {
    handleSubmit (name) {
        this.$refs[name].validate((valid) => {
            if (valid) {
                this.$Message.success('Success!');
            } else {
                this.$Message.error('Fail!');
            }
        })
    },
    handleReset (name) {
        this.$refs[name].resetFields();
    }
  }
}
</script>
