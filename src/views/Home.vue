<template>
  <div>
    <b-jumbotron>
      <b-container>
        <b-row class="jumbo-text">
          <b-col lg="6" md="6" sm="12">
            <h1 class="display-2">Stream State</h1>
            <h2 class="lead">Real Time. Real Simple. Real Results.</h2> <!-- someone please change this -->
          </b-col>
        </b-row>
      </b-container>
    </b-jumbotron>

    <b-container>
      <b-card-group columns class="my-5">
        <b-card v-for="item in items" :key="item.id">
          <b-card-body>
            <b-card-title><a :href="item.link">{{ item.title }}</a></b-card-title>
            <b-card-text>{{ item.body }}</b-card-text>
          </b-card-body>
        </b-card>
      </b-card-group>
      <b-link to="/dashboard" class="my-5">Go to Dashboard</b-link>
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
  .jumbotron {
    background: url("https://www.dropbox.com/s/64oqwwslsctfz8q/grid-3227320_1920.jpeg?raw=1") no-repeat center center fixed; 
    background-size: cover;
    height: 70vh;
    margin: auto;
  }
  .jumbo-text {
    margin-top: 12%;
  }
</style>