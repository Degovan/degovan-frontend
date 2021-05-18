<template>
    <section class="hero">
        <div class="head-text"> 
            <span>Selamat Datang</span>
            <h1>Mulai Karirmu bersama kami disini</h1>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil, excepturi quis hic alias velit aliquid rerum impedit, ducimus, a aperiam culpa commodi laborum! Voluptas, eum?</p>
            <a href=""><i class="zmdi zmdi-phone"></i> Call me</a>
        </div>
        <div class="illustration">
            <img src="/images/degovan-hero.png" alt="degovan-hero">
        </div>
    </section>
</template>

<style lang="scss" scoped>
    .hero {
        display: flex;
        align-items: center;
        gap: 6rem;
        min-height: 100vh;
        margin-top: -15vh;

        @include for-size('lg') {
            gap: 1rem;
        }

        @include for-size('md') {
            flex-direction: column-reverse;
            min-height: unset;
            margin-top: 2rem;
        }

        @include for-size('xs') {
            margin-top: unset;
        }

        .head-text {
            flex: 8;
            display: flex;
            flex-direction: column;
            justify-content: center;
            font-family: $poppins;

            @include for-size('md') {
                justify-content: flex-start;
                align-items: center;
                padding: 0 1rem;
            }

            @include for-size('xs') {
                padding: 0 0rem;
            }

            span {
                font-weight: 700;
                color: $purple;
                font-size: 1.125rem;
            }

            h1 {
                margin-top: 27px;
                color: #000000;
                font-weight: 700;
                font-size: 3rem;
                line-height: 55px;

                @include for-size('lg') {
                    font-size: 2.5rem;
                }

                @include for-size('xs') {
                    font-size: 2rem;
                    line-height: 47.5px;
                    text-align: center;
                }
            }

            p {
                color: #404040;
                font-weight: 400;
                line-height: 24px;
                margin-top: 7px;
                padding-right: 10rem;

                @include for-size('md') {
                    text-align: center;
                    padding: 0 1rem;
                    margin-top: 1rem;
                }
            }

            a {
                background: $purple;
                border-radius: 10px;
                color: #FFFFFF;
                font-weight: 700;
                font-family: $poppins;
                font-size: 1.375rem;
                align-self: flex-start;
                text-decoration: none;
                padding: .9rem 2.25rem;
                margin-top: 41px;

                @include for-size('lg') {
                    font-size: 1.15rem;
                    margin-top: 35px;
                    padding: .8rem 2.1rem;
                }

                @include for-size('md') {
                    margin: 1.5rem auto 2.25rem;
                }

                i {
                    margin-right: .5rem;
                }
            }
        }

        .illustration {
            flex: 6;

            @include for-size('lg') {
                flex: 5;
            }

            img {
                width: 100%;

                @include for-size('md') {
                    width: 350px;
                }

                @include for-size('sm') {
                    width: 100%;
                }
            }
        }
    }

    @include for-size('md') {
        .hero {
            

            .head-text {
                

                h1 {
                    text-align: center;
                }

                p {
                    
                }
            }

            .illustration {

                img {
                    
                }
            }
        }
    }
</style>