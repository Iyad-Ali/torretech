<template>
    <div :key="skill.id" v-for="skill in skills">
        <Skill :skill="skill" />
    </div>
</template>

<script>
import Skill from "./Skill"
export default {
    name: "Skills",
    props: {
        skills: Array,
    },
    components: {
        Skill
    }
}
</script>