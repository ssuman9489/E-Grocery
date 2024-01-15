<template>
  <v-app style="background-color: rgb(157, 201, 201);">
    <navbar />
   <div class="container mt-5" >
    
    <h2>Contact Us</h2>

    <form @submit.prevent="submitForm" style="background-color: rgb(157, 201, 201);">
      <div class="mb-3" >
        <label for="name" class="form-label">Name</label>
        <input type="text" v-model="formData.name" class="form-control" id="name" required>
      </div>
      <div class="mb-3">
        <label for="email" class="form-label">Email</label>
        <input type="email" v-model="formData.email" class="form-control" id="email" required>
      </div>
      <div class="mb-3">
        <label for="subject" class="form-label">Subject</label>
        <input type="text" v-model="formData.subject" class="form-control" id="subject" required>
      </div>
      <div class="mb-3">
        <label for="message" class="form-label">Message</label>
        <textarea v-model="formData.message" class="form-control" id="message" rows="4" required></textarea>
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
 
  
   
    </div>
    <Footer />
  </v-app>
  
  </template>
 
  <script>
  import Navbar from "../components/Navbar";
  import Footer from "../components/Footer";

  export default {
    
    components: {
      Navbar,
      Footer
       
     },
     data() {
    return {
      formData: {
        name: '',
        email: '',
        subject: '',
        message: '',
      },
    };
  },
  methods: {
    submitForm() {
      // Handle form submission logic here
      console.log('Form submitted:', this.formData);
      // You can implement AJAX request or any other logic to handle form submission
    },
  },
};
  
  
  </script>
  <style scoped>
  .container {
  max-width: 600px;
  margin: 0 auto;
}

form {
  background-color: #f8f9fa;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h2 {
  text-align: center;
  color: #007bff;
}

label {
  font-weight: bold;
}

input,
textarea {
  width: 100%;
  padding: 10px;
  margin-bottom: 15px;
  border: 1px solid #292b2d;
  border-radius: 4px;
  box-sizing: border-box;
}

button {
  background-color: #1c354f;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}
  
.contact {
        
 text-align: center;
      }
.footer {
  background-color: #2c2525;
  padding: 20px;
  margin-bottom: 100px;
  box-shadow: 0px -2px 5px rgba(0, 0, 0, 0.1);
  text-align: center;
      }
      @media only screen and (min-width: 600px) {
    .top {
      margin-top: 70px;
    }
  }
  @media only screen and (min-width: 768px) {
    .top {
      margin-top: 120px;
    }
  }
  </style>