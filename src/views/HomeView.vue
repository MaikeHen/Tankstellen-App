<template>
  <div class="home">
    <img
      class="blue-filter"
      src="../assets/kisspng-filling-station-computer-icons-fuel-dispenser-gaso-gas-pump-5ac69d854a01d6.7160340615229658933031.png"
      alt="Zapfsäule"
      width="100"
      height="100"
    />
  </div>
  <div class="gasstations">
    <TankstellenSuche
      :gasstations="gasstations"
      @StreetSearchInput="console.log('hello')"
    />
  </div>
  <div class="sortfunction">
    <SortierOption :gasstations="gasstations" />
  </div>
  <div>
    <ul>
      <li v-for="gasstation in gasstations" :key="gasstation.objectid">
        {{ gasstation.attributes.adresse }}
      </li>
    </ul>
  </div>
</template>

<script>
import TankstellenSuche from "@/components/TankstellenSuche.vue";
import SortierOption from "@/components/SortierOption.vue";

export default {
  name: "HomeView",
  components: {
    TankstellenSuche,
    SortierOption,
  },
  data() {
    return {
      gasstations: [],
    };
  },
  created() {
    this.fetchGasstations();
  },
  methods: {
    async fetchGasstations() {
      const response = await fetch(
        "https://geoportal.stadt-koeln.de/arcgis/rest/services/verkehr/gefahrgutstrecken/MapServer/0/query?where=objectid+is+not+null&text=&objectIds=&time=&geometry=&geometryType=esriGeometryEnvelope&inSR=&spatialRel=esriSpatialRelIntersects&distance=&units=esriSRUnit_Foot&relationParam=&outFields=*&returnGeometry=true&returnTrueCurves=false&maxAllowableOffset=&geometryPrecision=&outSR=4326&havingClause=&returnIdsOnly=false&returnCountOnly=false&orderByFields=&groupByFieldsForStatistics=&outStatistics=&returnZ=false&returnM=false&gdbVersion=&historicMoment=&returnDistinctValues=false&resultOffset=&resultRecordCount=&returnExtentOnly=false&datumTransformation=&parameterValues=&rangeValues=&quantizationParameters=&featureEncoding=esriDefault&f=pjson"
      );
      const data = await response.json();
      this.gasstations = data.features;
    },
  },
};
</script>

<style>
.blue-filter {
  filter: invert(38%) sepia(58%) saturate(953%) hue-rotate(1deg)
    brightness(105%) contrast(91%);
}
.gasstations {
  padding: 2rem;
}
ul {
  list-style-type: none;
}
li {
  padding: 1rem;
}
</style>
