<script setup>
import { PatientCard } from 'fire-starters';
import PatientFHIRJson from './json/patient.json';
</script>

<script>

  export default {
    components: {
      PatientCard,
    },
    data() {
      return {
        fhirJson: PatientFHIRJson,
      };
    },
  };
</script>

<template>
  <patient-card :data="fhirJson">
    <template #toolbarTemplate>
       <button
      class="btn btn-primary dropdown-toggle text-wrap base-btn-download"
          type="button"
          data-bs-toggle="dropdown"
          aria-expanded="false"
        >
          Download
        </button>
        <ul class="dropdown-menu base-btn-download-dropdown">
          <li
            class="dropdown-item base-btn-download-dropdown-item base-btn-download-dropdown-item-json"
          >
            JSON
          </li>
          <li
            class="dropdown-item base-btn-download-dropdown-item base-btn-download-dropdown-item-xml"
          >
            XML
          </li>
          <li
            class="dropdown-item base-btn-download-dropdown-item base-btn-download-dropdown-item-pdf"
          >
            PDF
          </li>
        </ul>
  </template></patient-card>
</template>

<style>
</style>