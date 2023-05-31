<script setup>
import TableRow from '../components/TableRow.vue'

const data = [
  ["Alarmy (Premium)", "Audio reminders, tactile feedback, snoozable, paid ($4.99/month)", "https://apps.apple.com/us/app/alarmy-alarm-clock-sleepsound/id1163786766", "4.8/5 ⭐"],
  ["Coalarm", "Audio reminders, free", "https://apps.apple.com/no/app/voice-alarm-clock-coalarm/id1586940322", "Not rated"],
  ["Cozi Family Organizer", "Includes calendar, syncs with group, free", "https://apps.apple.com/us/app/cozi-family-organizer/id407108860", "4.8/5 ⭐"],
  ["Google Calendar", "Tactile feedback, includes calendar, syncs with group, free", "https://apps.apple.com/us/app/google-calendar-get-organized/id909319292", "4.6/5 ⭐"],
  ["Talk to me Alarm Clock", "Audio reminders, tactile feedback, free", "https://apps.apple.com/us/app/talk-to-me-alarm-clock/id1535616112", "3.5/5 ⭐"],
  ["Reminder (with voice)", "Audio reminders, tactile feedback, picture reminders, includes calendar, paid ($1.99)", "https://apps.apple.com/us/app/reminder-reminders-with-voice/id1071899483", "4.7/5 ⭐"]
]
</script>

<template>
  <table>
    <tr>
      <th class="name">Name</th>
      <th class="details">Details</th>
      <th class="link">Link to app store</th>
      <th class="rating">Rating</th>
    </tr>
    <TableRow v-for="row in data" :row="row" />
  </table>
</template>

<style>
table {
  margin-left: auto;
  margin-right: auto;
  margin-top: 30px;
  overflow-y: auto;
  width: 80%;
  text-align: left;
  font-family: 'Rubik', sans-serif;
  border-collapse: collapse;
}

th,
td {
  border-bottom: 1.5px solid #e6e6e6;
  padding: 10px 10px 10px 0;
}

.name {
  width: 17%;
}

.details {
  width: 46%;
}

.link {
  width: 25%;
}

.rating {
  width: 13%;
}

.tablewrap {
  overflow: auto;
}
</style>
