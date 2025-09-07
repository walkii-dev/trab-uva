<template>
  <div>
    <h1 class="intro">Conheça nossos cursos!</h1>
  </div>
  <div class="courses-list">
      <card-curso
        v-for="c in courses"
        :key="c.name"
        :course="c"
      />
  </div>
  <div class="enroll-title">
    <h2>Matricule-se já!</h2>
  </div>
  <form @submit.prevent="validSignUp" id="signup-form">
    <div class="input-container">
      <label for="name">Digite seu nome completo:</label>
      <input type="text" class="input-form" v-model="userName" @input="validarNome" placeholder="Digite aqui..." required></input>
    </div>
    <div class="input-container">
      <label for="email">Digite seu e-mail:</label>
      <input type="email" class="input-form" v-model='userEmail' placeholder="Insira aqui seu e-mail..." required></input>
    </div>
    <div class="input-container">
      <label for="course">Selecione o curso desejado:</label>
      <select class="input-form" v-model="userSelectedCourse">
        <option value="Selecione seu curso..." selected disabled hidden>Selecione seu curso...</option>
        <option v-for="c in courses" :key="c.id" :value="c.id">
      {{ c.title }}
        </option>    
      </select>
    </div>
    <div class="input-container-btn">
      <input type="submit" class="submit-btn" value ="Matricular"></input>
    </div>
    <div class="errorMessage">
      <p v-if="erro" class="erro">{{ erro }}</p>
    </div>
  </form>
</template>

<script setup>
import CardCurso from './components/CardCurso.vue';
import { ref } from 'vue'

const userName = ref('')
const userEmail = ref('')
const userSelectedCourse = ref('Selecione seu curso...')
const erro = ref('')

function validSignUp() {
  const nomeRegex = /^[a-zA-Z\sÀ-ÿ]+$/;

  
  if (!nomeRegex.test(userName.value)) {
    erro.value = 'O nome não pode conter números ou símbolos.';
    return;
  }

  if (userName.value === '' || userEmail.value === '' || userSelectedCourse.value === 'Selecione seu curso...') {
    erro.value = 'Por favor, preencha todas as informações.'
    return
  }

  erro.value = '';
  alert("Matrícula feita com sucesso!");
}


const courses = ref([
{ id: 3, title: "Introdução à Malandragem Digital", description: "Como identificar e escapar das armadilhas online mais comuns", hours: 6 },
{ id: 4, title: "Jogos de Azar Descomplicados", description: "Entenda as mecânicas e riscos por trás de joguinhos como o famoso 'do tigrinho'", hours: 10 },
{ id: 5, title: "Golpes Clássicos da Internet", description: "Um passeio histórico pelos maiores trambiques já aplicados online (modo museu)", hours: 5 },
{ id: 6, title: "Segurança contra Estelionato 2.0", description: "Aprenda como a IA pode ser usada tanto para o bem quanto para tentar te enganar", hours: 8 },
{ id: 7, title: "Sobrevivendo ao Mundo da Malandragem", description: "Técnicas de autodefesa digital e como não cair em ciladas", hours: 7}
]);
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Epunda+Slab:ital,wght@0,300..900;1,300..900&family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');
.courses-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1rem;
  margin-top: 1rem;
}

#signup-form{
  font-family: 'Montserrat', Arial;
  font-size: 20px;
  margin: 0 auto;
  max-width: 420px;
}

.input-form{
  font-family: 'Montserrat', sans-serif;
  border-radius: 8px;
  font-size: 22px;
  padding:6px;
  border: 2px solid gray;
}

.input-container-btn{
  display: flex;
  flex-direction: column;
  gap: 8px;
  padding-bottom: 24px;
  align-items: center;
}
.submit-btn{
    padding: 3px;
    border-radius: 8px;
    border: 2px solid black;
    text-decoration: none;
    color:black;
    align-content: center;
    width:120px;
    height: 40px; 
    text-align: center;
    font-family: 'Montserrat', sans-serif;
    font-size:14px;
    font-weight: bold;
    cursor: pointer;
}

.input-container{
  display: flex;
  flex-direction: column;
  gap: 8px;
  padding-bottom: 24px;
}

.intro{
font-family: 'Epunda Slab', Arial;
display: flex;
justify-content: center;
}

.enroll-title{
font-family: 'Epunda Slab', Arial;
display: flex;
justify-content: center;
padding-bottom: 24px;
}

label{
  font-weight: bold;
}

.erro {
  color: red;
}
</style>
