<template>
    <div>
        <app-header title="Authors"></app-header>
        <template>
            <v-card class="mx-auto" tile>
                <v-list dense>
                    <v-list-item v-for="(item, i) in authors" :key="i">
                        <v-list-item-content>
                            <v-list-item-subtitle>{{ item.name }}</v-list-item-subtitle>
                        </v-list-item-content>

                        <v-list-item-icon>
                            <div>
                                <v-menu offset-y>
                                    <template v-slot:activator="{ on, attrs }">
                                        <v-btn v-bind="attrs" v-on="on" text>
                                            <v-icon>mdi-dots-vertical</v-icon>
                                        </v-btn>
                                    </template>
                                    <v-list>
                                        <v-list-item>
                                            <v-list-item-title>Edit</v-list-item-title>
                                            <v-icon>mdi-pencil</v-icon>
                                        </v-list-item>
                                        <v-list-item>
                                            <v-list-item-title>Delete</v-list-item-title>
                                            <v-icon>mdi-delete</v-icon>
                                        </v-list-item>
                                    </v-list>
                                </v-menu>
                            </div>
                        </v-list-item-icon>
                    </v-list-item>
                </v-list>
            </v-card>
        </template>
    </div>
</template>

<script>
import authorsList from "@/data/authors.json";
import AppHeader from '@/components/AppHeader.vue';
    export default {
    components: { AppHeader },
        data() {
            return {
                authors: authorsList
            }
        },
        
    }
</script>

<style lang="scss" scoped>

</style>