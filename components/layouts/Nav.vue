<template>
    <nav>
        <Container>
            <div class="logo">
                <h1>Degovan</h1>
            </div>
        </Container>
    </nav>
</template>

<script>
import Container from '~/components/reusable/Container';

export default {
    components: {
        Container,
    }
}
</script>

<style lang="scss" scoped>
    nav {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 15vh;
        display: flex;
        align-items: center;

        @include for-size('md') {
            height: 13vh;
        }

        @include for-size('xs') {
            height: 10vh;
        }

        h1 {
            font-family: $poppins;
            font-size: 2.25rem;
            font-weight: 300;

            @include for-size('xs') {
                font-size: 1.7rem;
            }

            &::first-letter {
                font-weight: 700;
                color: $purple;
            }
        }
    }
    
</style>