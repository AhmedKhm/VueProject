<template>
    <div>
        <div class="navBar">
                <b-button v-b-toggle.sidebar-1 ><b-icon-list></b-icon-list></b-button>
                
        </div>
         <div>
            <b-sidebar id="sidebar-1" title="Menu" shadow width="15%">
            <div class="px-1 py-2">
                <p>
                Cras mattis consectetur purus sit amet fermentum. Cras justo odio, dapibus ac facilisis
                in, egestas eget quam. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.
                </p> <br/><br/><br/>
                  <b-button variant="outline-danger" class="mb-2" >
                 <nuxt-link to="/">  <b-icon icon="power" aria-hidden="true"></b-icon>Se déconnecter</nuxt-link> 
                  </b-button>
                
            </div>
            </b-sidebar>
        </div>
        
        <div class="section">
          <div class="profile">
                <img src="../assets/default-profile.png" alt="" />
                <b-form-file  class="mt-3" plain label-size="sm"></b-form-file><br/>
                
            </div>
            <div class="details">
                <h5>Ajouter des personnes certifiés:</h5> 
                   
                    <input type="input" class="form__field" placeholder="Nom"   required />
                    <input type="input" class="form__field" placeholder="Prenom"   required />
                    <input type="input" class="form__field" placeholder="Diplome"   required />
                    <input type="input" class="form__field" placeholder="Specialite"   required />
                    <input type="input" class="form__field" placeholder="Poste actuel"   required />
                    <input type="input" class="form__field" placeholder="Entreprise"   required />
                    <input type="input" class="form__field" placeholder="Secteur"   required />
                    <input type="input" class="form__field" placeholder="Certification"   required /><br/>
                    <div class="csbtn">
                    <b-button variant="success"> <b-icon-plus ></b-icon-plus> Ajouter</b-button>
                    </div>
            </div>
        </div>
    </div>
</template>

<script>
import { BIcon, BIconArrowUp, BIconArrowDown } from 'bootstrap-vue'
import { BootstrapVueIcons } from 'bootstrap-vue'
import 'font-awesome/scss/font-awesome.scss'


    export default {
        name:"EspaceAdmin",
         BIcon,
         BIconArrowUp,
         BIconArrowDown
    }
</script>

<style lang="scss" scoped>

.navBar{
    background-color: rgb(237, 241, 241);
    width: 100%;
    height: 6vh;
}
.section {
  background-color: rgb(237, 241, 241);
  width: 70%;
  height: 32rem;
  margin: 3rem 0rem 0rem 15rem;
  border-radius: 1rem;
  display: flex;
}
.profile {
  color: black;
  margin: 1rem 0rem 1rem 1rem;
  width: 17rem;
  height: 29rem;
  border: 2px solid;
  border-radius: 10px;
  border-color: rgb(204, 202, 202);
  img {
    margin-left: 2rem;
  }
  h5 {
    margin-left: 5rem;
    color: rgb(56, 55, 55);
  }
  b-form-file{
      width: 20%;
  }
}
.details {
  margin: 1rem 0rem 1rem 1rem;
  width: 40rem;
  height: 29rem;
  border: 2px solid;
  border-radius: 10px;
  border-color: rgb(204, 202, 202);
h6{
    margin-left: 1rem;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    color: rgb(128, 126, 126);
}
h5{
    margin-left:1rem;
    color: blue;
}
input{
    margin-top: 2rem;
    margin-left: 3rem;
}
.csbtn{
    margin-left: 28rem;
}
}
$gray: #9b9b9b; 
.form__field {
  margin-bottom: 1rem;
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
</style>