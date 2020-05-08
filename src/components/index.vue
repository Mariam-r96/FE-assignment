<template>

<div id="main">
         <div id="one">
                    <div class="header">
                        <h2>10 Best Photo Apps For Incredible iPhone Photography (2020 Edition)</h2>
                        <hr>
                    </div>
                    <section class="section1">
                        <p class="para1">How do you capture more interesting travel photos with your iPhone? How do you avoid taking the same cliché vacation photos that everyone else takes? I recently 
                            interviewed Steffen Geldner – a talented iPhone photographer with a passion for travel. In this article, Steffen reveals 7 tips for shooting beautiful travel photos that will preserve 
                            the amazing memories of your trip. Read on to discover how to take better travel photos with your iPhone!</p>
   
                         <div class="imageContainer">
                                <!-- <img src="../assets/img@2x-1.jpg" alt=""> -->
                              
                             
                         </div> 
                    </section>
                    <section class="section2">
                        <h2>1. Research Your Destination To Find The Best Photo Opportunities</h2> 
                        <p>Before your trip, I recommend researching the destination to find the most interesting photo opportunities.</p>
                        <p>I always research the location I’m traveling to. I do this extensively and obsessively!</p>
                        <p>It’s up to you how much research you do. But you should definitely spend a bit of time looking up some great places to take pictures.</p>
                        <p>So, what kind of research can you do?</p>
                        <p>First, you could search for photos that other people have taken at the locations you’re planning to visit.</p>
                        <p>Search on Instagram or Google to get an idea of the kinds of photos people take there.</p>
                    </section>

                    <section class="section3">
                        <h2>2. Capture Your Journey To Tell The Complete Story Of Your Travels</h2> 
                        <p>Travel photography isn’t just about photographing the destination.</p>
                        <p>For a more complete photographic story, capture your journey to and from the location you’re visiting.</p>
                        <p>If you’re traveling by plane, try to get a window seat where you have a view of the wing or propeller.</p>
                        <p>And of course, you could capture a beautiful aerial view of clouds, mountains, or city lights as you’re flying above.</p>
                        <p>Your journey will often involve several different types of transport. And they all offer great photo opportunities.</p>
                        <p>Whether you’re traveling by car, taxi, bus, train, boat, or plane, try to capture some interesting photos.</p>
                    </section>
                </div>
                <div id="two">
                    <div class="tips_Btn" @click="showModal = true">
                        <p>Send Me The Tips</p>
                    
                    </div>
                </div>
               

                

            <div  class="modal" v-if="showModal">
         
                    <div class="modal-content">
           
                     <span class="close"  @click="showModal = false">&times;</span>
                        <div class="signUp-container">

                            <div class="stepProgress">
                                <p>Step 1 of 2</p>
                                <div class="progressBar-wrapper">
                                    <div class="progressBar"></div>
                                </div>
                            </div>
                            <div class="text-container">
                              <p class="text">Enter Your Email To Get <span style="color: #007A02;">FREE</span>
                                  iPhone Photography Email Tips: </p>
                            </div>
                            <form id="app" ref="form" @submit="checkForm" action="#" method="post" novalidate="true">
                                <div>
                                    <input type="email" class="inputText" name="email" v-model="email">

                                    <label class="initialPlaceholder" v-if="showValidPlaceholder">Please enter your email</label>
                                    <label class="error" v-if="showError">Please enter a valid email</label>
                                </div>
                            
                                <div class="send_btn" v-on:click="submit"><p> Send Me The Tips >></p></div>
                         </form>
                        </div>
                  </div>
             
         </div>
</div>

</template>


<script src="../retina/retina.min.js"></script>
<script>
export default{
  data(){
    return{
    errors:[],
    email:null,
    showModal: true,
    showError: false,
    showValidPlaceholder: true
    }
  },

  methods: {
    checkForm:function(e) {
      this.errors = [];
      if(!this.email) {
        this.errors.push("Email required.");
        this.showError=true;
        this.showValidPlaceholder=false;
       
      } else if(!this.validEmail(this.email)) {
        this.errors.push("Valid email required.");  
        this.showError=true;
        this.showValidPlaceholder=false;
        
      }
      if(!this.errors.length) return true;
      e.preventDefault();
     
    },
    validEmail:function(email) {
      var re = /^[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/;
    return re.test(email);
    },

    submit : function(e){
   
      this.errors = [];
      if(this.validEmail(this.email) && this.email ) {
        
        this.$refs.form.submit();
       
      }
      else if(!this.validEmail(this.email)) {
        this.errors.push("Valid email required.");  
        this.showError=true;
        this.showValidPlaceholder=false;
        
      }

          e.preventDefault();
    }

   
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

@import "../css/main.css";

/* 
 ** for sass styles **
 
@import "../scss/main.scss"; 
*/

*, *::before, *::after {
	box-sizing: border-box;
}

@media screen and (min-width: 1024px) and (max-width: 1366px){
.modal-content{
 width: 42%;
}
}


@media screen and (min-width: 768px) and (max-width: 1024px){
.modal-content{
 width: 76%;
}
 
}

@media screen and (min-width: 320px) and (max-width: 568px){
.text {
    width: 289px;
    height: 56px;
    font-weight: bold;
    font-size: 19px;
    line-height: 28px;
    color: #464646;
}

.progressBar-wrapper {
    left: 4.5rem;
    width: 57%;
}
 
}
 @media screen and (max-width: 480px) {
   .modal-content{
  width: 92%;
      height: 310px;
}

 #app{
  top: 8rem;
  left: -6rem;
}
 .text-container{
  
    margin-left: -2.5rem;
}
.stepProgress{
  left: -7rem;
  top: -0.5rem;
}

.progressBar-wrapper{
    left: 5.3rem;
    width: 67%;
}

#app input{
  width: 108%;
    margin-left: -1.6rem;
    padding-left: 11px;
    height: 49px;
    margin-top: 3px;
}

.send_btn {
     width: 109%;
    left: -1.7rem;
}
#app form div label {
left: -10px;
    font-size: 18px;
    top: 15px;
}
}

</style>