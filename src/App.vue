<script setup>
import { PatientCard, PatientTable, ImmunizationCard, ImmunizationTable } from 'fire-starters';
import PatientFHIRJson from './json/patient.json';
import PatientTableFHIRJson from './json/patient-table.json'; 
import ImmunizationCardFHIRJson from './json/immunization-card.json';
import ImmunizationTableFHIRJson from './json/immunaization-table.json';

</script>

<script>

  export default {
    components: {
      PatientCard,
      PatientTable,
      ImmunizationCard,
      ImmunizationTable
    },
    data() {
      return {
        fhirJson: PatientFHIRJson,
        patientTable: PatientTableFHIRJson,
        immunizationCard: ImmunizationCardFHIRJson,
        immunizationTable: ImmunizationTableFHIRJson
      };
    },
  };
</script>

<template>
  <h4>Patient Card</h4>
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
    </template>
  </patient-card>
  
  <h4 class="pt-3">Patient Table</h4>
  <patient-table :data="patientTable"></patient-table>
  
  <h4 class="pt-3">Immunization Card</h4>
  <immunization-card :data="immunizationCard"></immunization-card>
  
  <h4 class="pt-3">Immunization Table</h4>
  <immunization-table :data="ImmunizationTableFHIRJson"></immunization-table>
</template>

<style>
 h4 {
   text-align: left;
 }
</style>