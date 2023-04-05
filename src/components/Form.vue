<template>
    <div>
        <h1>Search for a person</h1>
        <form @submit.prevent="search">
            <label for="name">Name:</label>
            <input type="text" id="name" v-model="searchQuery" />
            <button type="submit">Search</button>
        </form>
        <div v-if="person">
            <h2>{{ person.name }}</h2>
            <img :src="person.image" alt="Person" />
            <h3>Skills:</h3>
            <ul>
                <li v-for="skill in person.skills" :key="skill">{{ skill }}</li>
            </ul>
        </div>
        <div v-else-if="searchQuery">
            <p>No results found for "{{ searchQuery }}"</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Form',
    data() {
        return {
            searchQuery: '',
            person: null,
        };
    },
    methods: {
        async search() {
            // Use an API to retrieve the person's data based on the search query
            const response = await fetch(`https://torre.bio/api/bios/${this.searchQuery}`);
            const data = await response.json();

            if (data.length > 0) {
                // Update the component's data properties with the retrieved data
                this.person = {
                    name: data[0].name,
                    image: data[0].image,
                    skills: data[0].skills,
                };
            } else {
                // Clear the person data if no results were found
                this.person = null;
            }
        },
    },
};
</script>