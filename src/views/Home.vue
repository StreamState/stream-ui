<template>
  <div>
    <b-container>
      <b-card-group columns class="my-5">
        <b-card v-for="item in items" :key="item.id">
          <b-card-body>
            <b-card-title><a :href="item.link">{{ item.title }}</a></b-card-title>
            <b-card-text>{{ item.body }}</b-card-text>
          </b-card-body>
        </b-card>
      </b-card-group>
      <router-link to="/dashboard" class="my-5">Go to Dashboard</router-link>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "Home",
  data: () => ({
    items: [
      {
        id: 0,
        title: "Argo",
        body: "A robust workflow engine for Kubernetes that enables the implementation of each step in a workflow as a container.",
        link: "/ui",
      },
      {
        id: 1,
        title: "Monitoring",
        body: "View and manage metrics, logs, traces, alerts, and notifications.",
        link: "/monitoring",
      },
      {
        id: 2,
        title: "Graphs",
        body: "Interacrtive charts, graphs, and alerts for the web when connected to supported data sources.",
        link: "/grafana",
      },
      {
        id: 3,
        title: "Spark History",
        body: "A monitoring tool that displays information about completed Spark applications.",
        link: "/sparkhistory",
      },
      {
        id: 4,
        title: "API Docs",
        body: "Instructions on how to effectively use and integrate Stream State with an API(s).",
        link: "/docs",
      },
    ],
  }),
};
</script>

<style scoped>
#editor {
  overflow-y: hidden;
}
#output .card {
  height: 85vh;
  overflow-y: scroll;
}
#editor .card {
  height: 85vh;
  overflow-y: scroll;
  background: #f7f7f7;
}
.my-editor {
  background: #f7f7f7;
  color: #ccc;
  font-family: Fira code, Fira Mono, Consolas, Menlo, Courier, monospace;
  font-size: 0.7rem;
  line-height: 1.5;
  overflow-y: scroll;
}
.prism-editor__textarea:focus {
  outline: none;
}
.hidden {
  visibility: hidden;
}
</style>