<template>
<v-container class="my-5">
    <h1>Profil de {{login}}</h1>

      <v-card flat class="pa-5" color="#E1DBF9">
        <v-layout row>
          <v-flex class="pa-5 ProfilePage">

            <!-- Image de profil de l'utilisateur -->
            <v-avatar size="300">
              <img src="../../assets/PlayerProfil.png" alt="Profil" />
            </v-avatar>
          </v-flex>

          <v-flex pa-5>

            <!-- Infos de l'utilisateur -->
            <v-flex class="mb-3" xs12 md12 lg12>
              <span class="title"> Pseudo </span>
              <br/>
              <span class="infos">{{ login }} </span>
            </v-flex>

            <v-flex class="mb-3" xs12 md12 lg12>
              <span class="title"> Mot De Passe </span>
              <br/>
              <span class="infos"> ********** </span>
            </v-flex>

            <v-flex class="mb-3" xs12 md12 lg12>
              <span class="title"> Adresse Email </span>
              <br/>
              <span class="infos"> {{ email }} </span>
            </v-flex>

            <v-flex class="mb-3" xs12 md12 lg12>
              <span class="title"> Nombre de parties jouées </span>
              <br/>
              <span class="infos"> {{ nbGames }} </span>
            </v-flex>
          </v-flex>

        </v-layout>
      </v-card>
    </v-container>

</template>

<script>
export default {
  data: () => ({
    login: "",
    password: "",
    email: "",
    nbGames: ""
  }),
  mounted: function() {
    this.getInfos();
  },
  methods : {
    getInfos() {
      this.login = this.$store.state.user.pseudo;
      this.email = this.$store.state.user.email;
      this.nbGames = this.$store.state.user.nbGames;
    },
  }

}
</script>


<!-- CSS de la page -->
<style>
.profile {
  text-align: center;
  font-size: 25px;
  font-weight: bold;
}

h1 {
  text-align: center;
  margin-top: 1%;
  margin-bottom: 1%;
}

.ProfilePage {
  text-align: center;
}

.title {
  color:grey;
}

.infos {
  font-weight: bold;
}

</style>