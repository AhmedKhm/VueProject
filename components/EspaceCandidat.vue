<template>
  <div>
    <div class="navBar">
      <b-button v-b-toggle.sidebar-1><b-icon-list></b-icon-list></b-button>
    </div>
    <div>
      <b-sidebar id="sidebar-1" title="Menu" shadow width="15%">
        <div class="px-1 py-2">
          <p>
            Cras mattis consectetur purus sit amet fermentum. Cras justo odio,
            dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta
            ac consectetur ac, vestibulum at eros.
          </p>
          <br /><br /><br />
          <b-button variant="outline-danger" class="mb-2">
            <nuxt-link to="/">
              <b-icon icon="power" aria-hidden="true"></b-icon>Se
              déconnecter</nuxt-link
            >
          </b-button>
        </div>
      </b-sidebar>

      <div class="section">
        <div class="profile">
          <img src="../assets/default-profile.png" alt="" />
          <b-form-file class="mt-3" plain label-size="sm"></b-form-file><br />
          <h5>Jhon Doe</h5>
          <h5 font-size="1px">
            <b-icon-envelope></b-icon-envelope> jhonDoe@gmail.com
          </h5>
          <h5><b-icon-phone></b-icon-phone> 54321654</h5>
        </div>
        <div class="details">
          <h5>Mon Profile:</h5>
          <br /><br />
          <div class="disposition">
            <div>
              <h6>Nom : Jhon <b-icon-pencil-square></b-icon-pencil-square></h6>
              <h6>
                Diplome : ingenieur informatique
                <b-icon-pencil-square></b-icon-pencil-square>
              </h6>
              <h6>
                Poste Actuel: developpeur fullstack
                <b-icon-pencil-square></b-icon-pencil-square>
              </h6>
            </div>
            <div class="dispoRight">
              <h6>
                Prenom : Doe <b-icon-pencil-square></b-icon-pencil-square>
              </h6>
              <h6>
                Specialite : genie logiciel
                <b-icon-pencil-square></b-icon-pencil-square>
              </h6>
              <h6>
                Nom d'entreprise :Sofrecom
                <b-icon-pencil-square></b-icon-pencil-square>
              </h6>
            </div>
          </div>
          <h4>Description:</h4>
          <br />
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi
            sapiente quaerat, rem minus quasi aspernatur deserunt consectetur,
            voluptas odit ullam voluptate perferendis totam natus iure harum
            magni minima repellendus! Cum et corrupti odio, adipisci ea
            eligendi? Aliquam aperiam, provident adipisci consequatur
            perspiciatis, delectus sint ab tempora a illo nihil beatae!
          </p>
          <div class="csbtn">
            <b-button variant="success">
              <b-icon-pencil></b-icon-pencil> Modifier</b-button
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "EspaceCandidat"
};
</script>

<style lang="scss" scoped>
.navBar {
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
    margin-left: 3rem;
    color: rgb(110, 108, 108);
  }
  b-form-file {
    width: 20%;
  }
}
p {
  margin-left: 1rem;
}
h4 {
  color: blue;
  margin-left: 1rem;
}
.details {
  margin: 1rem 0rem 1rem 1rem;
  width: 40rem;
  height: 29rem;
  border: 2px solid;
  border-radius: 10px;
  border-color: rgb(204, 202, 202);
  h6 {
    margin-left: 1rem;
    font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
    color: rgb(128, 126, 126);
  }
  h5 {
    margin-left: 1rem;
    color: blue;
  }
  input {
    margin-top: 2rem;
    margin-left: 3rem;
  }
  .csbtn {
    margin-left: 28rem;
  }
}
.disposition {
  display: flex;
}
.dispoRight {
  margin-left: 5rem;
}
</style>
