<template>
    <form>
        <label for="titleInput" id="titleInputLabel">Title:</label>
        <input type="text" id="titleInput" v-model="title"/>

        <label for="contentInput" id="contentInputLabel">Content:</label>
        <input type="text" id="contentInput" v-model="content"/>

        <label for="dateInput" id="dateInputLabel">Date:</label>
        <input type="date" id="dateInput" v-model="date" />
    </form>
</template>

<script>
export default {
    name: 'NoteInput',
    data : function() {
        return {
            title: "Title",
            content: "Content",
            date: '2018-02-03'
        }
    },
    methods: {
        initialiseDate: function() {
            const today = new Date();
            const currDay = today.getDate();
            const currMonth = `${today.getMonth() + 1}`;
            const currYear = today.getFullYear();

            this.date = `${currYear}-${currMonth.padStart(2, 0)}-${currDay}`
        }
    },
    created() {
        this.initialiseDate();
    },
}
</script>

