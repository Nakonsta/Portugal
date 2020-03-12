<template>
    <v-app>
        <v-navigation-drawer absolute temporary v-model="drawer" class="d-lg-none">
            <v-list>
                <v-list-item v-for="(item, i) in menuItems" :key="i" :to="item.route">
                    <v-list-item-action>
                        <v-icon v-html="item.icon"></v-icon>
                    </v-list-item-action>
                    <v-list-item-content>
                        <v-list-item-title>{{item.title}}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
        <v-app-bar dark app class="primary">
            <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="d-lg-none"></v-app-bar-nav-icon>
            <v-toolbar-title v-text="'Learning Portugal'"></v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items class="d-none d-lg-block">
                <v-btn text v-for="(item, key) in menuItems" :key="key" :to="item.route">
                    <v-icon left v-html="item.icon"></v-icon>
                    {{item.title}}
                </v-btn>
            </v-toolbar-items>
        </v-app-bar>
    </v-app>
</template>

<script>
export default {
    name: 'AppHeader',

    data() {
        return {
            drawer: false
        }
    },

    computed: {
        menuItems() {
            return [
                {
                    icon: 'mdi-cube',
                    title: 'Читать',
                    route: '/books'
                },
                {
                    icon: 'mdi-cursor-pointer',
                    title: 'Учить слова',
                    route: '/words'
                },
                {
                    icon: 'mdi-account-circle-outline',
                    title: 'Мой кабинет',
                    route: '/profile'
                },
                {
                    icon: 'mdi-logout',
                    title: 'Выйти',
                    route: '/logout'
                },
                {
                    icon: 'mdi-login',
                    title: 'Войти',
                    route: '/signin'
                },
                {
                    icon: 'mdi-account-plus',
                    title: 'Зарегистрироваться',
                    route: '/signup'
                }
            ]
        }
    }
}

</script>

<style scoped>

</style>