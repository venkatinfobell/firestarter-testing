<script setup>
import { PatientCard, PatientTable } from 'fire-starters';
import PatientFHIRJson from './json/patient.json';
import patientTableFHIRJson from './json/patient-table.json'; 
</script>

<script>

  export default {
    components: {
      PatientCard,
      PatientTable
    },
    data() {
      return {
        fhirJson: PatientFHIRJson,
        patientTable: patientTableFHIRJson
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
  
  <patient-table :data="patientTable" class="pt-2"></patient-table>
</template>

<style>
</style>