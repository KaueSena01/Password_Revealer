<template>
  <div class="container">
      <form>
        <div class="logo">
          <ion-icon name="log-out-outline"></ion-icon>
        </div>
        <h1>Login</h1>
        <p>Faça seu login</p>
        <div class="form-items">
          <label for="Nome">Nome:</label>
          <input type="text" placeholder="Seu nome completo" class="input-area">
        </div>

        <div class="form-items">
          <label for="Senha">Senha:</label>
          <input 
          :type="inputType" 
          placeholder="Digite uma senha segura" class="input-area" >

          <div class="Revealing" @click="togglePassword">

          <ion-icon v-if="isPassword" name="eye-outline"></ion-icon>
          <ion-icon v-else name="eye-off-outline"></ion-icon>
          </div>
        </div>

        <div class="form-items">
          <input type="submit" class="input-area" value="Enviar">
        </div>
      </form>
    </div>
</template>

<script>
  export default {
    name: 'PasswordRevealing',

    data() {
      return {
        inputType: 'password'
      }
    },

    computed: {
      isPassword() {
        return this.inputType === 'password';
      }
    },

    methods: {
      togglePassword() {
        this.inputType = this.isPassword ? 'text' : 'password';
      }
    },
  }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap');
  
  *{
    margin:  0;
    padding: 0;
    border: 0;
    outline: none;
    font-family: 'Poppins';
    box-sizing: border-box;
  }
  .container{
    min-height: 350px;
    min-width: 350px;
    background-color: white;
    margin: 0 auto;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 5px;
    box-shadow: 1px 5px 10px #cac9c9;
  }
  form{
    width: 95%;
    margin: 0 auto;
    text-align: center;
  }
  form .logo{
    max-width: 30px;
    padding-top: 20px;
    margin: auto;
  }
  .logo ion-icon{
    width: 30px;
    height: 30px;
    color: #64acba;
  }
  form h1{
    font-size: 30px;
    color: #64acba;
  }
  form p{
    font-size: 14px;
    margin-bottom: 20px;
  }
  .form-items{
    width: 100%;
    height: 60px;
    margin-top: 5px;
    display: flex;
    flex-direction: column;
  }
  .form-items label{
    font-size: 13px;
    text-align: left;
  }
  .form-items input{
    width: 100%;
    height: 38px;
    background-color: #f9f9f9;
    padding-left: 8px;
    font-size: 13px;
  }
  .form-items ion-icon{
    position: absolute;
  }
</style>