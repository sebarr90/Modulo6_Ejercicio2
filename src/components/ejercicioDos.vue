<template>
  <div class="form-container">
    <form @submit.prevent="enviarFormulario" class="form">
      <h2>Formulario</h2>

      <div class="form-group">
        <label for="nombre">Nombre:</label>
        <input type="text" id="nombre" v-model="nombre" required>
      </div>

      <div class="form-group">
        <label for="apellido">Apellido:</label>
        <input type="text" id="apellido" v-model="apellido" required>
      </div>

      <div class="form-group">
        <label for="correo">Correo:</label>
        <input type="email" v-model="correo" id="correo" required>
      </div>

      <button type="button" @click="enviarFormulario" class="submit-button">Enviar</button>
    </form>

    <hr>

    <form class="age-form">
      <div class="form-group">
        <label for="edad">Edad:</label>
        <input type="number" v-model="edad" id="edad" required>
      </div>

      <div class="age-message">
        <div v-if="edad<0">Tiene que ser un número mayor a cero!!!</div>
        <div v-else-if="edad > 0 && edad <= 13">Estás en la Niñez</div>
        <div v-else-if="edad > 13 && edad <= 17">Estás en la Adolescencia</div>
        <div v-else-if="edad > 17 && edad <= 35">Eres Adulto Joven</div>
        <div v-else-if="edad > 35 && edad <= 64">Eres Adulto</div>
        <div v-else-if="edad > 64">Eres Adulto Mayor</div>
      </div>
    </form>
  </div>
</template>

<style>
.form-container {
  max-width: 500px;
  margin: 0 auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  background-color: #f9f9f9;
}

.form {
  display: flex;
  flex-direction: column;
}

.form-group {
  margin-bottom: 15px;
}

label {
  margin-bottom: 5px;
  font-weight: bold;
}

input[type="text"],
input[type="email"],
input[type="number"] {
  margin: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 16px;
}

input[type="text"]:focus,
input[type="email"]:focus,
input[type="number"]:focus {
  margin: 10px;
  border-color: #007BFF;
  outline: none;
}

.submit-button {
  padding: 10px;
  border: none;
  border-radius: 4px;
  background-color: #007BFF;
  color: white;
  font-size: 16px;
  cursor: pointer;
}

.submit-button:hover {
  background-color: #0056b3;
}

.age-message {
  margin-top: 10px;
  font-size: 40px;
  color: #333;
  text-align: center;
}
</style>


<script>
export default {
  name: 'ejercicioDos',
  data: function () {
    return {
      nombre: '',
      apellido: '',
      correo: '',
      edad: 0,
    }
  },
  methods: {
    enviarFormulario: function () {
      if(this.nombre!==""&& this.apellido!==""&&this.correo!==""){
      alert(`Saludos ${this.nombre} ${this.apellido} tu correo es: ${this.correo}`);
      }else{
        alert("Por favor completa todos los campos");
      }
    }
  }
}
</script>
