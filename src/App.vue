<template>
  <button class="notification" @click="showNotifications = !showNotifications">
    <img :src="bell" />
    <span class="badge">3</span>
  </button>
  <div v-if="showNotifications" class="popup">
    <div class="popup-content">
      <h3 class="h3Class">Notificaciones</h3>
      <ul>
        <li v-for="notification in notificationList" :key="notification.id">
          <div>
           
            <p style="color: white; font-size: 11px">
              <b> {{ notification.titulo }}</b>
              <br />
              {{ notification.ubicacion }}
              <br />{{ notification.fecha }} | {{ notification.hora }}
            </p>
          </div>
        </li>
      </ul>
    </div>
  </div>
  <div id="contenedor">
    <iframe
      id="inlineFrameExample"
      src="https://ide.igp.gob.pe/portal/apps/experiencebuilder/experience/?id=69c335f953ca42b5b2137a2c59b8d340"
      style="width: 100%; height: 100%; border: 0"
      @load="iframeLoad"
    />
  </div>
</template>

<script setup>
import { ref } from "vue";
import bell from "../public/bell.svg";

const showNotifications = ref(false);

const notificationList = [
  {
    id: 1,
    titulo: "ALERTA DE DECENSO DE LAHAR",
    ubicacion: "Volcán Sabancaya",
    fecha: "01/03/2024",
    hora: "3:30 p.m.",
  },
  {
    id: 2,
    titulo: "ALERTA DE DISPERSIÓN DE CENIZAS",
    ubicacion: "Volcán Sabancaya",
    fecha: "01/03/2024",
    hora: "3:30 p.m.",
  },
  {
    id: 3,
    titulo: "BOLETÍN VULCANOLOGICO",
    ubicacion: "Volcán Sabancaya",
    fecha: "01/03/2024",
    hora: "3:30 p.m.",
  },
];
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");
* {
  font-family: "Poppins", sans-serif;
}

.notification {
  background-color: #555;
  color: white;
  text-decoration: none;
  padding: 5px 35px;
  position: absolute;
  display: inline-block;
  border-radius: 50px;
  z-index: 10;
  right: 3%;
  top: 6%;
  cursor: pointer;
}

.notification:hover {
  background-color: rgba(0, 0, 0, 0.637);
  background-color: rgba(0, 0, 0, 0.637);
}

.notification .badge {
  position: absolute;
  top: -3px;
  right: 25px;
  padding: 1px 5px;
  border-radius: 50%;
  background: white;
  color: red;
}

.popup {
  z-index: 9;
  position: absolute;
  top: 12%;
  right: 10px;
  background-color: rgba(0, 0, 0, 0.637);
  border-radius: 20px;
  padding: 0px 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.h3Class {
  color: white;
  border-bottom: 2px solid;
  border-color: white;
  display: flex;
  justify-content: center;
}

.popup-content {
  overflow-y: none;
}

.popup-content ul {
  list-style-type: none;
  color: white;
}

.popup-content ul li {
  margin-bottom: 10px;
  color: white;
}

#contenedor {
  height: auto;
  position: absolute;
  top: 0px;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
}
</style>
