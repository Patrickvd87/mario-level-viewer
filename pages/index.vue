<template>
  <div>
    <h1>Popular levels:</h1>
    <ul>
      <li v-for="course in courses">
        {{ course.name }}
      </li>
    </ul>
  </div>
</template>

<script setup>
const {data: courses} = await useFetch('https://tgrcode.com/mm2/search_popular?count=10&difficulty=e', {
  transform: data => data['courses'],
});
</script>
