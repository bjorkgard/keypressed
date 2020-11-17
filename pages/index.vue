<template>
  <div class="flex flex-col content-center pt-20 min-h-screen">
    <div class="container mx-auto min-h-full flex flex-col flex-1">
      <div class="text-5xl font-extrabold text-center text-gray-700">
        Press any key
      </div>
      <div
        class="text-center font-black leading-relaxed text-purple-700"
        style="font-size: 200px"
      >
        {{ event ? event.keyCode : '&nbsp;' }}
      </div>
      <div class="flex justify-around">
        <panel>
          <template #header>event.key</template>
          <template>{{ event ? event.key : '&nbsp;' }}</template>
        </panel>
        <panel>
          <template #header>event.location</template>
          <template>{{ event ? event.location : '&nbsp;' }}</template>
        </panel>
        <panel>
          <template #header>event.which</template>
          <template>{{ event ? event.which : '&nbsp;' }}</template>
        </panel>
        <panel>
          <template #header>event.code</template>
          <template>{{ event ? event.code : '&nbsp;' }}</template>
        </panel>
      </div>
    </div>
    <nat-footer />
  </div>
</template>

<script>
import Panel from '../components/Panel'
import NatFooter from '../components/Footer'

export default {
  components: {
    Panel,
    NatFooter,
  },
  data() {
    return {
      event: null,
    }
  },
  mounted() {
    window.addEventListener('keydown', this.getKeyboard)
  },
  beforeDestroy() {
    window.removeEventListener('keydown', this.getKeyboard)
  },
  methods: {
    getKeyboard(event) {
      this.event = event
    },
  },
}
</script>
