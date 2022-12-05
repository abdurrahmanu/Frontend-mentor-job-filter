<template>
  <div class="home">
    <Background_header />
    <Search_bar
    v-if="!hide_searchBar"
    @del="filter_and_delete_jobCard"
    @clear="hide_searchBar = true"
    :data="search_items"
    />
    <Job_card
    v-for="(data, i) in data"
    :key="i"
    :data="data"
    />
  </div>
</template>

<script setup>
import Job_card from './components/job_card.vue';
import Search_bar from './components/search_bar.vue';
import Background_header from './components/svgs/bg_header.vue';
import all_data from '../data.json';
import { ref } from 'vue';

const data = ref(all_data)
const search_items = ref()
const hide_searchBar = ref(false)

let skills_and_tools = data.value.map(each => {
  return each.languages.concat(each.tools)
}).flat()

//remove duplicate skills
search_items.value = skills_and_tools.reduce((acc, char) => {
  return acc.includes(char) ? acc : [...acc, char]
}, [])

const filter_and_delete_jobCard = (item) => {
  data.value = data.value.filter(each => !each.tools.includes(item) && !each.languages.includes(item))
  search_items.value = search_items.value.filter(each => each !== item)
  if (!search_items.value.length || !data.value.length) hide_searchBar.value = true
}

</script>


