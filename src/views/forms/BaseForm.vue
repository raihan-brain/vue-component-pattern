<template>
  <div class="container-lg">
    <div class="container">
      <div class="row justify-content-md-center">
        <div class="col-md-auto">
          <movie-component
            :image="'sadfsdfsdf'"
            :length="190"
            :title="'Saving private ryan'"
            :have-seen-movie="true"
          >
            <template v-slot:reference>
              <p>testing slot</p>
            </template>
            <template v-slot:hero="slotProps">
              <h1>{{ slotProps.logo }}</h1>
            </template>
            <template v-slot:default>
              <h1>default</h1>
            </template>
          </movie-component>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MovieComponent from "@/components/baseComponents/MovieCompoenet.vue";
export default defineComponent({
  components: {
    MovieComponent,
  },
});
</script>

<style scoped></style>
