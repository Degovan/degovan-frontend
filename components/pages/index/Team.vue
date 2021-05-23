<template>
    <section class="team">
        <div class="head">
            <h1 class="title">Team Kami siapa saja?</h1>
            <div class="buttons d-none-mobile">
                <button @click="generateTeamsPosition('left')"><i class="zmdi zmdi-chevron-left"></i></button>
                <button @click="generateTeamsPosition('right')"><i class="zmdi zmdi-chevron-right"></i></button>
            </div>
        </div>
        <div class="teams">
            <div class="card" v-for="member in generatedTeams" :key="member.id">
                <img :src="member.image" alt="">
                <h4>{{ member.name }}</h4>
                <h3>{{ member.role }}</h3>
            </div>
        </div>
        <div class="buttons d-none-dekstop">
            <button @click="generateTeamsPosition('left')"><i class="zmdi zmdi-chevron-left"></i></button>
            <button @click="generateTeamsPosition('right')"><i class="zmdi zmdi-chevron-right"></i></button>
        </div>
    </section>
</template>

<script>
export default {
    props: {
        teams: {
            type: Array,
            required: true
        }
    },
    data() {
        return {
            dataTeams: this.teams,
        }
    },
    computed: {
        generatedTeams() {
            return this.dataTeams;
        }
    },
    methods: {
        generateTeamsPosition(direction) {
            let newGeneratedTeams = [];

            if( direction == 'right' ) {
                this.dataTeams.forEach((member, index) => {
                    if( index == 0 ) {
                        newGeneratedTeams[ this.dataTeams.length - 1 ] = member;
                    } else {
                        newGeneratedTeams[ index - 1 ] = member;
                    }
                });
            } else if( direction == 'left' ) {
                this.dataTeams.forEach((member, index) => {
                    if( index == this.dataTeams.length - 1 ) {
                        newGeneratedTeams[ 0 ] = member;
                    } else {
                        newGeneratedTeams[ index + 1 ] = member;
                    }
                });
            }
            this.dataTeams = newGeneratedTeams;
        }
    }
}
</script>

<style lang="scss" scoped>
    section.team {
        font-family: $poppins;
        padding: 108px 0;

        @include for-size('md') {
            padding: 75px 0;
        }

        @include for-size('xs') {
            padding: 45px 0;
        }

        .head {
            display: flex;
            align-items: center;
            justify-content: space-between;

            @include for-size('md') {
                flex-direction: column;
            }

            h1.title {
                color: $dark-purple;
                font-weight: 600;
                font-size: 2.25rem;

                @include for-size('md') {
                    text-align: center;
                }

                @include for-size('xs') {
                    font-size: 1.9rem;
                }
            }
        }

        .teams {
            display: flex;
            align-items: flex-start;
            justify-content: space-between;
            gap: 1rem;
            margin-top: 62px;

            @include for-size('md') {
                margin-top: 50px;
            }

            @include for-size('sm') {
                margin-top: 35px;
            }

            @include for-size('xs') {
                flex-direction: column;
                gap: 2rem;
            }

            .card {
                width: 100%;
                display: none;

                &:nth-child(1) {
                    display: block;
                }

                &:nth-child(2) {
                    display: block;
                }

                &:nth-child(3) {
                    display: block;
                }

                @include for-size('xs') {
                    &:nth-child(1) {
                        display: block;
                    }

                    &:nth-child(2) {
                        display: none;
                    }

                    &:nth-child(3) {
                        display: none;
                    }
                }

                img {
                    width: 100%;
                    height: 442px;
                    object-fit: cover;
                    object-position: center;

                    @include for-size('lg') {
                        height: 340px;
                    }

                    @include for-size('md') {
                        height: 270px;
                    }

                    @include for-size('sm') {
                        height: 185px;
                    }

                    @include for-size('xs') {
                        height: 350px;
                    }
                }

                h4 {
                    margin-top: 1rem;
                    color: #828282;
                    font-size: 0.813rem;
                    font-weight: 500;

                    @include for-size('xs') {
                        margin-top: .4rem;
                    }
                }

                h3 {
                    font-size: 1.5rem;
                    font-weight: 600;

                    @include for-size('md') {
                        font-size: 1.35rem;
                    }

                    @include for-size('sm') {
                        font-size: 1.2rem;
                    }
                }
            }
        }

        .buttons {
            display: flex;
            align-items: center;
            gap: .5rem;

            button {
                width: 36px;
                height: 36px;
                border-radius: 18px;
                border: 1px solid $purple;
                opacity: .5;
                display: flex;
                align-items: center;
                justify-content: center;
                background: #FFFFFF;
                font-size: 1.55rem;
                font-weight: 300;
                color: $purple;
                transition: all 300ms ease;

                &:hover {
                    opacity: 1;
                    cursor: pointer;
                }
            }
        }

        .d-none-dekstop {
            display: none;
            justify-content: center;
            margin-top: 1.15rem;

            @include for-size('md') {
                display: flex !important;
            }
        }

        .d-none-mobile {
            @include for-size('md') {
                display: none;
            }
        }
    }
</style>