<script>
import AppSection from './AppSection.vue';
export default {
    components: {
        AppSection,
    }
}
</script>

<template>
    <main>
        <section>
            <p>--&gt; Content goes here &lt;--</p>
        </section>
        <AppSection />
    </main>
</template>

<style lang="scss" scoped>
@use "../style/partials/variables.scss";
@use "../style/partials/mixin.scss";

main {
    section:first-child {
        background-color: black;
        min-height: 80px;
        color: white;
        line-height: 100px;

        p {
            width: 70%;
            margin: 0 auto;
            font-size: 1.5rem;
            font-weight: 900;
        }

    }
}
</style>