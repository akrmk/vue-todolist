<template>
<v-app>
    <v-container class="my-5">
        <v-form @submit.prevent="add">
            <v-row class="my-5 mx-5">
                <v-text-field solo v-model="text"></v-text-field>
                <v-btn type="submit" class="mx-5" fab dark color="indigo">
                    <v-icon dark>mdi-plus</v-icon>
                </v-btn>
            </v-row>
        </v-form>
        <div v-for="(item,i) in items" v-bind:key="i" class="my-3 mx-5">
            <input type="checkbox" v-model="item.isChecked" />
            <label :class="{done : item.isChecked, 'ml-3': true}">{{item.text}}</label>
        </div>

    </v-container>
</v-app>
</template>

<style>
.done {
    text-decoration: line-through;
}
</style>

<script>
export default {
    name: "App",
    data: () => ({
        text: "",
        items: []
    }),
    methods: {
        add: function () {
            if (!this.text.trim()) {
                return
            }
            this.items.push({
                text: this.text,
                isChecked: false
            });
            this.text = "";
        },
    },
};
</script>
