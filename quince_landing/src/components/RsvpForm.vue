<script setup>
import { computed, reactive, ref } from 'vue'

const form = reactive({
  nombre: '',
  telefono: '',
  asistencia: 'Sí asistiré',
  acompanantes: 0,
  mensaje: ''
})

const sending = ref(false)
const status = ref('idle')
const errorMessage = ref('')

const endpoint = import.meta.env.VITE_RSVP_ENDPOINT

const buttonText = computed(() => {
  if (sending.value) return 'Enviando...'
  if (status.value === 'success') return 'Confirmación enviada'
  return 'Confirmar asistencia'
})

const resetStatus = () => {
  status.value = 'idle'
  errorMessage.value = ''
}

const saveLocalBackup = (payload) => {
  const key = 'confirmaciones-cata'
  const current = JSON.parse(localStorage.getItem(key) || '[]')
  current.push(payload)
  localStorage.setItem(key, JSON.stringify(current))
}

const submitForm = async () => {
  resetStatus()

  if (!form.nombre.trim()) {
    status.value = 'error'
    errorMessage.value = 'Por favor escribe tu nombre completo.'
    return
  }

  const payload = {
    nombre: form.nombre.trim(),
    telefono: form.telefono.trim(),
    asistencia: form.asistencia,
    acompanantes: Number(form.acompanantes || 0),
    mensaje: form.mensaje.trim(),
    fechaRegistro: new Date().toISOString()
  }

  sending.value = true

  try {
    if (!endpoint) {
      saveLocalBackup(payload)
      status.value = 'success'
      return
    }

    const response = await fetch(endpoint, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        Accept: 'application/json'
      },
      body: JSON.stringify(payload)
    })

    if (!response.ok) {
      throw new Error('No se pudo enviar la confirmación.')
    }

    status.value = 'success'
    form.nombre = ''
    form.telefono = ''
    form.asistencia = 'Sí asistiré'
    form.acompanantes = 0
    form.mensaje = ''
  } catch (error) {
    status.value = 'error'
    errorMessage.value = error.message || 'Ocurrió un error al enviar la confirmación.'
    saveLocalBackup(payload)
  } finally {
    sending.value = false
  }
}
</script>

<template>
  <form class="rsvp-form" @submit.prevent="submitForm">
    <p class="form-eyebrow">Confirma tu asistencia</p>
    <h2>¿Nos acompañas?</h2>

    <label>
      Nombre completo
      <input
        v-model="form.nombre"
        type="text"
        name="nombre"
        autocomplete="name"
        placeholder="Escribe tu nombre"
      />
    </label>

    <label>
      Celular
      <input
        v-model="form.telefono"
        type="tel"
        name="telefono"
        autocomplete="tel"
        placeholder="Opcional"
      />
    </label>

    <label>
      Confirmación
      <select v-model="form.asistencia" name="asistencia">
        <option>Sí asistiré</option>
        <option>No podré asistir</option>
      </select>
    </label>

    <label>
      Número de acompañantes
      <input
        v-model="form.acompanantes"
        type="number"
        name="acompanantes"
        min="0"
        max="10"
      />
    </label>

    <label>
      Mensaje opcional
      <textarea
        v-model="form.mensaje"
        name="mensaje"
        rows="3"
        placeholder="Déjale un mensaje a Cata"
      />
    </label>

    <button class="submit-button" type="submit" :disabled="sending">
      {{ buttonText }}
    </button>

    <p v-if="status === 'success'" class="form-message success">
      Gracias. Tu respuesta quedó registrada.
    </p>

    <p v-if="status === 'error'" class="form-message error">
      {{ errorMessage }}
    </p>

    <p v-if="!endpoint" class="form-note">
      Modo demo: configura <strong>VITE_RSVP_ENDPOINT</strong> para enviar las respuestas al cliente.
    </p>
  </form>
</template>
