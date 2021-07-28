<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid px-5">
        <a class="navbar-brand" href="#">Stream State</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav"></ul>
        </div>
      </div>
    </nav>

    <div class="container-fluid p-5">
      <div id="admin-list" class="row row-cols-1 row-cols-md-3 g-4">
        <div v-for="item in items" :key="item.id">
          <div class="col">
            <div class="card">
              <div class="card-body">
                <a :href="item.link">
                  <h5 class="card-title">{{ item.title }}</h5>
                </a>
                <p class="card-text">{{ item.body }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <router-link to="/dashboard">Go to Dashboard</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  el: "#admin-list",
  data: () => ({
    items: [
      {
        id: 0,
        title: "Argo",
        body: "Argo is a robust workflow engine for Kubernetes that enables the implementation of each step in a workflow as a container. It provides simple, flexible mechanisms for specifying constraints between the steps in a workflow and artifact management for linking the output of any step as an input to subsequent steps.",
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
        body: "A multi-platform open source analytics and interactive visualization web application. It provides charts, graphs, and alerts for the web when connected to supported data sources.",
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
        body: "A technical content deliverable, containing instructions about how to effectively use and integrate with an API.",
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