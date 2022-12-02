<template>
    <div id="search">
        <div class="items">
            <div v-for="(item, i) in data" :key="i" class="item">
                {{item}}
                <span @click="emits('del', item)">X</span>
            </div>
        </div>
        <div class="clear" @click="emits('clear')">clear</div>
    </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

const emits = defineEmits(['del', 'clear'])
const props = defineProps({ data: Array })
</script>




