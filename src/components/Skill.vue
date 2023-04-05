<template>
    <div class="skill">
        <h3>{{ skill.name }}</h3>
        <p>{{skill.proficiency}}</p>
    </div>
</template>

<script>

    export default{
        name:"Skill",
        props:{
            skill: Object,
        },
    }
</script>

<style scope>
.skill {
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
    border-left: 5px solid green;
}

.task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
}</style>