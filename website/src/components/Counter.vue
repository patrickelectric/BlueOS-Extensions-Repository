<template>
  <v-container>
<<<<<<< Updated upstream
    <v-row>
      <v-col v-for="extension in extensions" :key="extension.identifier">
        <v-card class="mx-auto" width="400px" outlined>
          <v-card-title>
            <v-row no-gutters class="justify-center align-center">
              <v-avatar tile size="50">
                <v-img :src="extension.extension_logo" />
              </v-avatar>
              <v-col>
                <v-card-title>
                  <a v-bind:href="extension.website">{{ extension.name }}</a>
                </v-card-title>
                <v-card-subtitle>
                  <a v-bind:href="'https://hub.docker.com/r/' + extension.docker">{{ extension.identifier }}</a>
                </v-card-subtitle>
              </v-col>
            </v-row>
          </v-card-title>
          <v-card-text>{{ extension.description }}</v-card-text>
        </v-card>
      </v-col>
=======
    <v-row
      v-for="(section, index) in sections"
      :key="index"
    >
      <h1>{{ section }}</h1>
      <v-row>
        <v-col v-for="extension in extensions" :key="extension.identifier">
          <v-card v-if="Object.values(extension.versions)[0].type === section" class="mx-auto" width="400px" outlined>
            <v-card-title>
              <v-row no-gutters class="justify-center align-center">
                <v-avatar tile size="50">
                  <v-img :src="extension.extension_logo" />
                </v-avatar>
                <v-col>
                  <v-card-title>
                    <a v-bind:href="extension.website">{{ extension.name }}</a>
                  </v-card-title>
                  <v-card-subtitle>
                    <a v-bind:href="'https://hub.docker.com/r/' + extension.docker">{{ extension.identifier }}</a>
                  </v-card-subtitle>
                  <v-card-actions>
                    <v-chip label class="ma-1" color="blue" v-for="tag in Object.values(extension.versions)[0].filter_tags">
                      {{ tag }}
                    </v-chip>
                  </v-card-actions>
                </v-col>
              </v-row>
            </v-card-title>
            <v-card-text>{{ extension.description }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
>>>>>>> Stashed changes
    </v-row>
  </v-container>
</template>

<script setup lang="ts">
<<<<<<< Updated upstream
import { onMounted, ref } from "vue";
import { RepositoryEntry } from "@/types/manifest"
=======
import { computed, onMounted, ref } from "vue";
import {ExtensionType, RepositoryEntry} from "@/types/manifest"
>>>>>>> Stashed changes

const extensions = ref();

onMounted(async () => {
<<<<<<< Updated upstream
  const response = await fetch("manifest.json");
=======
  const response = await fetch("manifest.json") ;
>>>>>>> Stashed changes
  extensions.value = await response.json() as [RepositoryEntry];
});

const sections = computed(() => {
  return ExtensionType
})
</script>
