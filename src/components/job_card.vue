<template>
<div id="container"  :class="{'featured': data.featured}">
        <div class="job">
            <div id="img">
                <img :src="data.logo" alt="">
            </div>
            <div id="about_job">
                <div class="company_name">
                    <div>{{data.company}}</div>
                    <div class="special" v-if="data.new">NEW!</div>
                    <div class="special" v-if="data.featured">FEATURED</div>
                </div>
                <div class="hob_position">{{data.position}}</div>
                <div class="more">
                    <div>{{data.postedAt}}</div>
                    <span>.</span>
                    <div>{{data.contract}}</div>
                    <span>.</span>
                    <div>{{data.location}}</div>
                </div>
            </div>
        </div>
        <hr>
        <div>
            <div>
                <Skill
            :languages="data.languages"
            :level="data.level"
            :role="data.role"
            :tools="data.tools"
                />
            </div>
        </div>
</div>
</template>

<script setup>
import Skill from './skill.vue'
import { defineProps } from 'vue';

const props = defineProps({ data: Object })
</script>









