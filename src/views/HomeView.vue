<template>
<app-layout class="home">
    <!-- <template #header>Slots are awesome</template> -->
    <!-- *** this example uses props *** -->
    <!-- <app-button text="Click me" :showIcon="true"></app-button> -->

    <!-- *** with SLOTS *** -->
    <!-- <template #default>
        <app-button @click="log()">
            Click Me
            <icon width="10" height="10" />
        </app-button>
    </template>
    <template #footer>Slots are awesome</template> -->
<app-user-list/>
</app-layout>
</template>

<script>
import appLayout from '@/views/appLayout';
import appButton from '@/components/appButton.vue';
import Icon from '@/components/Icon.vue'
import AppUserList from '@/components/AppUserList.vue'


export default {
    name: 'HomeView',
    components: {
        appButton,
        Icon,
        appLayout,
        AppUserList
    },
    methods: {
        log() {
            console.log("It works!")
        }
    }
}
</script>
