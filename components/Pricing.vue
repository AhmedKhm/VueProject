<template>
    <div>
        <div class="dispo">
            <div class="box">
                <div class="box1">
                    <h3>Gratuit</h3>
                    <h6>Pour seulement 24h</h6>
                   <nuxt-link to="/EspaceRecruteurPage"> <button variant="success">S'inscrire</button></nuxt-link>
                </div>

            </div>
            <div class="box">
                  <div class="box1">
                    <h3>Par mois</h3>
                    <h6>Renouvelable par carte bancaire</h6>
                    <button variant="success">S'inscrire</button>
                </div>
            </div>
            
            <div class="box">
                 <div class="box1">
                    <h3>Par an </h3>
                    <h6>Profiter d'une remise </h6>
                    <button variant="success">S'inscrire</button>
                </div>
             </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:"Pricing"
    }
</script>

<style lang="scss" scoped>

.box{
    background-color: rgb(221, 215, 215);
    width: 20rem;
    height: 25rem;
    margin-top: 7rem;
    margin-left: 7rem;
    border:2px solid;
    border-radius: 1rem;
    border-color: beige;
}
.dispo{
    display: flex;
}
.box1{
    h3{
        font-size: 5em;
        text-align: center;
        margin-top: 4rem;
    }
    h6{
        margin-left: 4rem;
        color: rgb(102, 102, 101);
    }
   button{
       margin-top: 7rem;
       margin-left: 1rem;
       width: 17rem;
       box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
       background-color: #4CAF50;
       border:2px thick;
       border: none;
       border-radius: 1rem;
   }
}

</style>