<template>
    <div class="sect">
      
      <div class="rectif">
           <img src="../assets/Programmer-2-512.png" alt=""> 
            <section class="loginBox">
                <h4>Connectez vous en tant que:</h4><br/><br/>
                <b-tabs content-class="mt-3">
                    <b-tab title="Administrateur" active>
                        <input type="input" class="form__field" placeholder="Identifiant"   required /><br/>
                        <input type="input" class="form__field" placeholder="Mot de passe"   required /> <br/>
                       <div class="btn">
                           <nuxt-link to="/EspaceAdminPage"> <b-button variant="success">Se connecter</b-button> </nuxt-link>
                        </div>
                    </b-tab>
                    <b-tab title="Candidat">
                        <input type="input" class="form__field" placeholder="Identifiant"   required /><br/>
                        <input type="input" class="form__field" placeholder="Mot de passe"   required /> <br/>
                         <div class="btn">
                         <nuxt-link to="/EspaceCandPage">   <b-button variant="success">Se connecter</b-button></nuxt-link>
                        </div>
                   </b-tab>
                    <b-tab title="Recruteur">
                        <input type="input" class="form__field" placeholder="Identifiant"   required /><br/>
                        <input type="input" class="form__field" placeholder="Mot de passe"   required /><br/>
                         <div class="btn">
                           <nuxt-link to="/PricingPage">  <b-button variant="success">Se connecter</b-button></nuxt-link>
                        </div>
                    </b-tab>
                </b-tabs>   
            </section>
      </div>
     
    </div>
</template>

<script>
    export default {
        name:"HomePage"
    }
</script>

<style lang="scss" scoped>
.sect{
  width:100vw;
  height: 100vh; 
  background-color:#3a60ad;
}
img{
  margin: 5rem 0rem 0rem 10rem;
}
.loginBox{
    background-color: rgb(189, 247, 247);
    width: 23rem;
    margin-left: 55rem;
    margin-top: -30rem;
    height: 25rem;
    border: 2px solid;
    border-radius: 1rem;
    border-color: aquamarine;
    h4{
        text-align: center;
        color: #3aada7;
        font-family: 'Times New Roman', Times, serif;
    }
}
.rectif{
    width: 100%;
    height: 100%;
}
$gray: #9b9b9b; 
.form__field {
  margin-bottom: 3rem;
  margin-left: 1rem;
  font-family: inherit;
  width: 30%;
  border: 0;
  border-bottom: 2px solid $gray;
  outline: 0;
  font-size: 1rem;
  color:  rgb(66, 65, 65);
  padding: 7px 0;
  background: transparent;
  transition: border-color 0.2s;

  &::placeholder {
    color: rgb(78, 77, 77);
  }

  &:placeholder-shown ~ .form__label {
    font-size: 1.3rem;
    cursor: text;
    top: 20px;
  }
}
.btn{
    margin-left: 4rem;
}
</style>