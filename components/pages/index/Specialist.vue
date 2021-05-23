<template>
    <section class="specialist">
        <h1>Spesialist Kami</h1>
        <p class="desc">Front-End, Backend, Design UI/UX, dan Mobile Apps</p>
        <ul class="skills">
            <li class="skill" v-for="i in 3" :key="i">
                <div class="icon">
                    <i class="zmdi zmdi-laptop"></i>
                </div>
                <div class="desc">
                    <h3>
                        Laravel
                    </h3>
                    <p>Backend developer dengan teknologi kekinian</p>
                </div>
            </li>
        </ul>
    </section>
</template>

<style lang="scss" scoped>
    section.specialist {
        margin-top: 121px;
        background-color: rgba(207, 202, 246, .25);
        padding: 2.063rem 0 15rem;
        font-family: $poppins;

        @include for-size('md') {
            padding-bottom: 5rem;
            margin-top: 80px;
        }

        @include for-size('sm') {
            padding: 1.25rem 1rem 4rem;
            margin-top: 50px;
        }

        h1 {
            font-size: 2.25rem;
            font-weight: 600;
            text-align: center;

            @include for-size('xs') {
                font-size: 1.9rem;
            }
        }

        p.desc {
            font-size: 0.813rem;
            font-weight: 300;
            text-align: center;
            margin-top: 9px;
        }

        ul.skills {
            display: flex;
            gap: 2rem;
            justify-content: center;
            align-items: center;
            margin-top: 5.35rem;

            @include for-size('md') {
                margin-top: 3rem;
            }

            @include for-size('sm') {
                gap: 1rem;
            }

            @include for-size('xs') {
                flex-direction: column;
                gap: 2rem;
            }

            li.skill {
                display: flex;
                align-items: flex-start;
                gap: 1.25rem;

                @include for-size('md') {
                    flex-direction: column;
                    align-items: center;
                }

                .icon {
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    width: 70px;
                    height: 70px;
                    border-radius: 35px;
                    color: #FFFFFF;
                    background: #FC5254;
                    font-size: 1.5rem;
                }

                .desc {
                    margin-top: 27.5px;

                    @include for-size('md') {
                        margin-top: 0;
                    }

                    @include for-size('xs') {
                        margin-top: -.55rem;
                    }

                    h3 {
                        font-size: 0.75rem;
                        font-weight: 700;

                        @include for-size('md') {
                            text-align: center;
                        }
                    }

                    p {
                        font-size: 0.75rem;
                        font-weight: 400;
                        width: 150px;
                        line-height: 18px;
                        color: #828282;
                        margin-top: 4px;

                        @include for-size('md') {
                            text-align: center;
                        }

                        @include for-size('xs') {
                            width: 200px;
                        }
                    }
                }
            }
        }
    }
</style>