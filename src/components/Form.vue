<template>
  <div class="hello">
   <form id="app" @submit="checkForm" action="#" method="post" novalidate="true">
  
  <p v-if="errors.length">
    <b>Please correct the following error(s):</b>
    <ul>
      <li v-for="error in errors" v-bind:key="error.id">{{ error }}</li>
    </ul>
  </p>
  

  <p>
    <label for="email">Email</label>
    <input type="email" name="email" id="email" v-model="email">
  </p>


  <p>
    <input type="submit" value="Submit">  
  </p>

</form>

  </div>
</template>


<script>

export default{
  data(){
    return{
    errors:[],
    email:null,
    }
  },

  methods: {
    checkForm:function(e) {
      this.errors = [];
      if(!this.email) {
        this.errors.push("Email required.");
      } else if(!this.validEmail(this.email)) {
        this.errors.push("Valid email required.");        
      }
      if(!this.errors.length) return true;
      e.preventDefault();
    },
    validEmail:function(email) {
      var re = /^[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/;
    return re.test(email);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
