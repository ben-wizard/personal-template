<template>
  <div class="projects">
    <div class="row justify-content-center">
      <div
        v-for="(project, i) in projects"
        :key="i"
        class="col-lg-4 col-md-6 col-sm-12 p-1"
      >
        <div
          @click="go(project.target)"
          style="display: flex; flex-direction: column"
          class="border-dotted-block quaternary"
        >
          <h3 class="tertiary">{{ project.name }}</h3>
          <p style="flex-grow: 1">{{ project.description }}</p>
          <div v-if="project.tags.length > 0" class="row p-2">
            <div
              v-for="(tag, j) in project.tags"
              :key="j"
              class="col-2 p-2 tag"
            >
              {{ tag }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        projects: [
          {
            name: "PHP Tools",
            description:
              "PHP ile yazılmış 2 adet kullanışlı araç.",
            tags: ["Proje", "PHP", "Açık Kaynak"],
            target: "https://github.com/ben-wizard/php-tools",
          },
          {
            name: "Permission Calculator",
            description:
              "Discord botları için yetki ayarlama sitesi.",
            tags: ["Proje", "Site", "Açık Kaynak"],
            target: "https://github.com/ben-wizard/permission-calculator",
          },
          {
            name: "Atlantis Register",
            description:
              "Discord Atlantis sunucusu için kodlanmış kayıt botu.",
            tags: ["Discord" ,"Register", "Atlantis"],
            target: "https://github.com/ben-wizard/wizard-atlantis-register",
          },
        ],
      };
    },

  methods: {
    go(str) {
      window.open(str);
    },
  },
};
</script>