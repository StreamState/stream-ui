<template>
  <div>
    <b-container fluid>
      <b-form-input
        class="my-5"
        id="filter-input"
        v-model="filter"
        type="search"
        placeholder="Type to Search"
      />
      <b-table
        :fields="fields"
        :items="provider"
        :filter="filter"
        :busy.sync="isBusy"
        hover
        responsive
      />
    </b-container>
  </div>
</template>

<script>
export default {
  name: "Dashboard",
  data: () => ({
    filter: null,
    fields: [
      { key: "job_name", sortable: true },
      { key: "spark_name", sortable: true },
      { key: "state", sortable: true },
      { key: "start_time", sortable: true },
      { key: "stop_time", sortable: true },
      { key: "execution_attempts", sortable: true },
      { key: "submission_attempts", sortable: true },
    ],
    isBusy: false,
  }),
  methods: {
    provider: () =>
      fetch("/api/applications", {
        method: "GET",
        credentials: "include",
      })
        .then((response) => response.json())
        .catch(() => []),
  },
};
</script>

<style>
table {
  font-size: 0.8em;
  white-space: nowrap;
}
th {
  background-color: whitesmoke !important;
}
</style>