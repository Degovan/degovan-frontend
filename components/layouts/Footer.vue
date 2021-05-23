<template>
    <footer>
        <Container>
            <div class="footer">
                <h2>Social media kami</h2>
                <a href=""><i class="zmdi zmdi-instagram"></i> @degovan</a>
                <hr>
                <span>Copyright By Degovan</span>
            </div>
        </Container>
    </footer>
</template>

<script>
import Container from '~/components/reusable/Container';

export default {
    components: {
        Container
    }
}
</script>

<style lang="scss" scoped>
    footer {
        background: #161525;
        margin-top: 60px;

        .footer {
            padding: 23px 0 16px;
            display: flex;
            flex-direction: column;
            align-items: center;

            h2 {
                font-family: $poppins;
                font-style: normal;
                font-weight: bold;
                font-size: 24px;
                line-height: 45px;
                color: $purple;

                @include for-size('sm') {
                    font-size: 20px;
                }
            }

            a {
                font-family: $poppins;
                font-style: normal;
                font-weight: 500;
                font-size: 18px;
                line-height: 45px;
                color: #857EF3;
                text-decoration: none;
                display: flex;
                align-items: center;

                @include for-size('sm') {
                    font-size: 16.5px;
                }

                i {
                    margin-right: 13px;
                    font-size: 2rem;

                    @include for-size('sm') {
                        font-size: 1.65rem;
                        margin-right: 11px;
                    }
                }
            }

            hr {
                width: 80%;
                border: 1px solid rgba(255, 255, 255, 0.25);
                margin-top: 30px;
            }

            span {
                margin-top: 10px;
                font-family: $poppins;
                font-style: normal;
                font-weight: normal;
                font-size: 14px;
                line-height: 45px;
                color: #828282;

                @include for-size('sm') {
                    font-size: 13.5px;
                }
            }
        }
    }
</style>