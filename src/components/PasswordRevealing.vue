<template>
  <div class="container">
      <form>
        <div class="logo">
          <ion-icon name="log-out-outline"></ion-icon>
        </div>
        <h1>Login</h1>
        <hr/>
        <div class="form-items">
          <label for="Nome">Nome:</label>
          <input type="text" placeholder="Seu nome completo" class="input-area">
        </div>

        <div class="form-items">
          <label for="Senha">Senha:</label>
          <input 
          :type="inputType" 
          placeholder="Digite uma senha" class="input-area" >

          <div class="Revealing" @click="togglePassword">

          <ion-icon v-if="isPassword" name="eye-outline"></ion-icon>
          <ion-icon v-else name="eye-off-outline"></ion-icon>
          </div>

        </div>
        <a href="#">Esqueceu a senha?</a>
        <div class="form-items">
          <button type="submit" class="input-area">Enviar</button>
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
  }
  form .logo{
    max-width: 30px;
    padding-top: 20px;
    margin: auto;
  }
  .logo ion-icon{
    width: 30px;
    height: 30px;
    color: #3fc5df;
  }
  form h1{
    font-size: 30px;
    color: #3fc5df;
    text-align: center;
  }
  form hr{
    margin: 0 35% 20px 35%;
    width: 30%;
    height: 2px;
    background-color: #c3c3c3;
    margin-bottom: 25px;
  }
  .form-items{
    width: 100%;
    height: 60px;
    margin-top: 10px;
    display: flex;
    flex-direction: column;
  }
  .form-items label{
    font-size: 13px;
    font-weight: 600;
    text-align: left;
    color: #7d7e7e;
  }
  .form-items input{
    width: 100%;
    height: 38px;
    border: 2px solid #eee;
    border-radius: 3px;
    padding-left: 8px;
    font-size: 13px;
    transition: all .2s ease;
  }
  .form-items input:focus{
    border: 2px solid #3fc5df;
    padding-left: 15px;
  }
  .Revealing{
    position: absolute;
    margin: 30px 300px;
  }
  .Revealing ion-icon{
    color: #c3c3c3;
  }
  form a{
    font-size: 13px;
    text-decoration: none;
    color: #15a1bc;
  }
  button{
    margin-top: 7px;
    width: 30%;
    padding: 7px;
    background-color: #3fc5df;
    border: 2px solid #3fc5df;
    border-radius: 3px;
    font-weight: bold;
    color: #fff;
    cursor: pointer;
    transition: all .2s ease;
  }
  button:hover{
    opacity: 0.9;
    border: 2px solid #15a1bc;
    border-radius: 3px;
  }
</style>