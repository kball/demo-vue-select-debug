<template>
  <section class="container">
    <div>
      <logo/>
      <h1 class="title">
        demo-vue-select-debug
      </h1>
      <h2 class="subtitle">
        An example of debugging
      </h2>
      <div class="links">
        <no-ssr>
          <v-select
            v-model="selected"
            :options="['foo','bar']"
          />
        </no-ssr>
      </div>
    </div>
  </section>
</template>

<script>
import NoSSR from 'vue-no-ssr'
const components = {
  'no-ssr': NoSSR
}

if (process.browser) {
  components['v-select'] = () => import('vue-select')
}

export default {
  components,
  data() {
    return {
      selected: null
    }
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
