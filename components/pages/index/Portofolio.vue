<template>
    <section class="portofolio">
        <div class="head">
            <h2 class="title">Portofolio</h2>
            <ul class="tabs">
                <li class="active">Website</li>
                <li>Mobile Apps</li>
                <li>Illustration</li>
            </ul>
        </div>
        <div class="portofolios">
            <div class="card" v-for="i in 6" :key="i">
                <img src="/examples/portofolio.png" alt="">
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    section.portofolio {
        @include for-size('md') {
            margin-top: 3rem;
        }

        .head {
            display: flex;
            align-items: center;
            justify-content: space-between;
            font-family: $poppins;

            @include for-size('md') {
                flex-direction: column;
            }

            h2.title {
                font-weight: 600;
                color: $dark-purple;
                font-size: 2.25rem;
            }

            ul.tabs {
                display: flex;
                align-items: center;
                gap: 2rem;
                list-style: none;

                @include for-size('md') {
                    margin-top: 1.15rem;
                }

                li {
                    color: #828282;
                    font-size: 1.125rem;
                    font-weight: 400;
                    text-align: center;

                    @include for-size('sm') {
                        font-size: .9rem;
                    }

                    &.active {
                        color: #000000;
                        font-weight: 700;
                        position: relative;

                        &::after {
                            content: '';
                            position: absolute;
                            bottom: -10px;
                            left: 0;
                            width: 48px;
                            height: 3px;
                            background: $purple;
                            display: block;
                            left: 50%;
                            margin-left: -24px;
                        }
                    }
                }
            }
        }

        .portofolios {
            width: 100%;
            display: grid;
            gap: 1.2rem;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            margin-top: 96px;

            @include for-size('lg') {
                margin-top: 55px;
            }

            @include for-size('sm') {
                grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            }

            .card {
                overflow: hidden;
                border-radius: 10px;
                cursor: pointer;

                img {
                    width: 100%;
                    transition: all 400ms ease;

                    &:hover {
                        transform: scale(1.1);
                    }
                }
            }
        }
    }

    @include for-size('lg') {
        section.portofolio {
            .portofolios {
            }
        }
    }
</style>