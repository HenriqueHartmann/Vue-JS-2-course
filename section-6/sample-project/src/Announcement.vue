<template>
    <div class="alert alert-info">
        <div class="announcement" v-if="announcement">
            <p>{{ announcement }}</p>
        </div>
        <div v-else>
            <p>No announcement yet.</p>
        </div>
    </div>
</template>

<script>
    import { eventBus } from './main'

    export default {
        data() {
            return {
                announcement: null
            };
        },
        created () {
            eventBus.$on('articleWasShared', (data) => {
                this.announcement = data.title + " was shared on " + data.media + "!"
            })
        }
    }
</script>
