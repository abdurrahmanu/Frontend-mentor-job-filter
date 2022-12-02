<template>
<div class="skills" >
    <div>{{role}}</div>
    <div>{{level}}</div>
    <div
    v-for="(item, i) in tools"
    :key="i">
    {{item}}
    </div>
    <div
    v-for="(item, i) in languages"
    :key="i">
        {{item}}
    </div>
</div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps(
    {
        languages: Array,
        role: String,
        level: String,
        tools: Array
    }
)
</script>
