<template>
  <div class="calendar-container">
    <q-table
      bordered
      :rows="calendarEvents"
      :row-key="(col) => col.value"
      :columns="columns"
      dark
      color="amber"
      separator="vertical"
      :rows-per-page-options="[5]"
    >
      <template v-slot:body="props">
        <q-tr :props="props">
          <q-td v-for="col in props.cols" :key="col.name" :props="props">
            <div class="horizontal-flex">
              {{ col.value }}
              <div class="horizontal-spacer"></div>
              <q-btn
                class="align-right"
                v-show="col.name === 'Title'"
                size=".7rem"
                color="primary"
                dense
                @click="props.expand = !props.expand"
                label="Details"
              />
            </div>
          </q-td>
        </q-tr>
        <q-tr v-show="props.expand" :props="props">
          <q-td colspan="500px">
            <p>Some Text in the expandable section</p>
            <q-btn color="blue" />
          </q-td>
        </q-tr>
      </template>
    </q-table>
  </div>
</template>

<script setup>
// Temp copy
// :rows="calendarEvents.value"          // This works, but reads all property names across the top

import HttpHelper from 'src/Utility/HttpHelper';
import { ref, onBeforeMount } from 'vue';

// let testData = [
//   {
//     StartDate: { StartDate: '2024-06-08T22:00:00.000Z', required: false },
//     StartYear: 2024,
//     EndDate: '2024-06-09T02:00:00.000Z',
//     Title: 'KCRM @ Lenexa Public Market',
//     Description:
//       'Casual games of Mahjong. All are welcome for some tile-slinging action.',
//     Location: 'Lenexa Public Market, 8750 Penrose Ln, Lenexa, KS 66219, USA',
//     LocationLink:
//       'http://maps.google.com/?q=Lenexa Public Market, 8750 Penrose Ln, Lenexa, KS 66219, USA',
//     EventTime: '5:00 PM - 9:00 PM',
//     EventDate: '{year: "2024", abbrevMonth: "Jan", abbrevDay: "mon"}',
//   },
//   {
//     StartDate: { StartDate: '2024-07-08T22:00:00.000Z', required: false },
//     StartYear: 2024,
//     EndDate: '2024-06-09T02:00:00.000Z',
//     Title: 'KCRM @ Lenexa Public Market',
//     Description:
//       'Casual games of Mahjong. All are welcome for some tile-slinging action.',
//     Location: 'Lenexa Public Market, 8750 Penrose Ln, Lenexa, KS 66219, USA',
//     LocationLink:
//       'http://maps.google.com/?q=Lenexa Public Market, 8750 Penrose Ln, Lenexa, KS 66219, USA',
//     EventTime: '5:00 PM - 9:00 PM',
//     EventDate: '{"year": "2024", "abbrevMonth": "Jan", "abbrevDay": "mon"}',
//   },
// ];

const columns = [
  {
    name: 'Date', // More like a key, isn't displayed
    label: 'Date (Year/Month/Day)', // The displayed name of the column
    field: (row) => row.EventDate, // The data to read in to that column
    format: (val) =>
      `${val.year} ${val.abbrevMonth} ${val.day} (${val.abbrevDay})`,
    align: 'left', // Alignment
    style: 'width: 150px',
  },
  {
    name: 'Title',
    label: 'Event',
    field: (row) => row.Title,
    align: 'center',
  },
];

const calendarEvents = ref([]);
const dataIsReady = ref(false);
//let calendarEvents = testData;

onBeforeMount(async () => {
  calendarEvents.value = await HttpHelper(); // testData; //HttpHelper();
  console.log(calendarEvents.value);
  dataIsReady.value = true;
});

// let rows = [
//   {
//     Month: 'Jan',
//     day: 'Sun',
//   },
//   { Month: 'Feb', day: 'Mon' },
//   { Month: 'Mar' },
//   { Month: 'Apr' },
//   { Month: 'May' },
//   { Month: 'Jun' },
//   { Month: 'Jul' },
//   { Month: 'Aug' },
//   { Month: 'Sep' },
//   { Month: 'Oct' },
//   { Month: 'Nov' },
//   { Month: 'Dec' },
// ];
</script>

<style>
.calendar-container {
  width: max-content;
  margin: auto;
}

.align-right {
  margin-right: 0;
  margin-left: auto;
}

.horizontal-spacer {
  width: 10px;
}
</style>
