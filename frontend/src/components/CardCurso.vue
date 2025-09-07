<script setup>
const props = defineProps({
  course: { type: Object, required: true }
});

const emit = defineEmits(["enroll"]);

</script>



<template>
    <div class="card">
<h3 class="title">{{ course.title }}</h3>
<p class="description">{{course.description}}</p>
<span class="hours">Carga Horária: {{course.hours}} h</span>
    </div>
</template>



<style>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');

.card{
    font-family: 'Montserrat',Arial;
    border: 2px solid #ccc;
    border-radius: 8px;
    padding: 1rem;
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    flex-direction: column;
}

.title{
    font-size:1.05rem; 
    font-weight:600; 
    margin:1px;
    padding-bottom: 3px; 
    justify-content: left;
}

.hours{
  padding:0.25rem 0.5rem;
  border-radius:6px;
}


.description{
  color:#333;
  font-size:0.95rem;
  margin:0;
  line-height:1.3;
}
</style>