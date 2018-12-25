<script>
import { KilometerUiSample } from './entry';
export default {
    name:  'KilometerUiLibDev', // vue library dev component
    components: {
        KilometerUiSample,
    },
}
</script>

<template>
    <div class="kilometer-ui-lib-dev">
        <kilometer-ui-sample></kilometer-ui-sample>
    </div>
</template>

<style scoped>
    .kilometer-ui-lib-dev {
        display: block;
        width: 400px;
        margin: 25px auto;
    }
</style>
