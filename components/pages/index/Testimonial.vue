<template>
    <section class="testimonial">
        <h1 class="title">Dengarkan apa kata client kami</h1>
        <div class="testimonials">
            <div class="card" v-for="testimonial in displayedTestimonial" :key="testimonial.id">
                <p class="testimonial-text">{{ testimonial.testimonial }}</p>
                <div class="user">
                    <img :src="testimonial.picture" alt="" class="profile">
                    <div class="detail">
                        <h4 class="name">{{ testimonial.name }}</h4>
                        <span class="role">{{ testimonial.role }}</span>
                    </div>
                </div>
            </div>
        </div>
        <div class="bullets">
            <span :class="selectedTestimonial == testimonial.id ? 'active' : ''" class="bullet" @click="setSelectedTestimonial(testimonial.id)" v-for="testimonial in testimonials" :key="testimonial.id"></span>
        </div>
    </section>
</template>

<script>
export default {
    props: {
        testimonials: {
            type: Array,
            required: true
        }
    },
    data() {
        return {
            selectedTestimonial: this.testimonials ? this.testimonials[0].id : '',
        }
    },
    computed: {
        displayedTestimonial() {
            let testimonials = this.testimonials.filter((e) => {
                return e.id == this.selectedTestimonial;
            });

            if( this.testimonials.length - 1 == this.testimonials.indexOf(testimonials[0]) ) {
                testimonials.push(this.testimonials[0]);
            } else {
                testimonials.push(this.testimonials[ this.testimonials.indexOf(testimonials[0]) + 1 ]);
            }

            return testimonials;
        }
    },
    methods: {
        setSelectedTestimonial(id) {
            this.selectedTestimonial = id;
        }
    }
}
</script>

<style lang="scss" scoped>
    section.testimonial {
        background: #F3F2FD;
        padding: 4.125rem 15.625rem 6.5rem;

        @include for-size('lg') {
            padding: 4.125rem 5.625rem 6.5rem;
        }

        @include for-size('md') {
            padding: 4.125rem 2.625rem 6.5rem;
        }

        @include for-size('md') {
            padding: 4.125rem 1rem 6.5rem;
        }

        h1.title {
            font-family: $poppins;
            font-weight: 600;
            line-height: 45px;
            text-align: center;
            font-size: 2.25rem;

            @include for-size('xs') {
                font-size: 1.9rem;
            }
        }

        .testimonials {
            display: flex;
            gap: 1rem;
            margin-top: 2.625rem;

            @include for-size('sm') {
                flex-direction: column;
            }

            .card {
                border-radius: 10px;
                box-shadow: 0px 100px 80px rgba(94, 84, 251, .07), 0px 41.78px 33.4px rgba(94, 84, 251, .0503), 0px 22.34px 17.87px rgba(94, 84, 251, .0417), 0px 12.52px 10.02px rgba(94, 84, 251, .035), 0px 6.65px 5.32px rgba(94, 84, 251, .0283), 0px 2.77px 2.21px rgba(94, 84, 251, .0197);
                padding: 40px;
                background: #FFFFFF;
                display: none;

                &:nth-child(1) {
                    display: block;
                }

                &:nth-child(2) {
                    display: block;
                }

                @include for-size('sm') {
                    &:nth-child(1) {
                        display: block;
                    }

                    &:nth-child(2) {
                        display: none;
                    }
                }
                

                p {
                    font-family: $poppins;
                    font-weight: 600;
                    font-size: 0.688rem;
                    line-height: 16.5px;
                    color: #383838;
                }

                .user {
                    margin-top: 50px;
                    display: flex;
                    align-items: center;
                    gap: 1rem;

                    img {
                        width: 60px;
                        height: 60px;
                        object-fit: cover;
                        object-position: center;
                        border-radius: 30px;
                    }

                    .detail {
                        display: flex;
                        flex-direction: column;
                        gap: 4px;

                        h4.name {
                            font-family: $poppins;
                            font-style: normal;
                            font-weight: 600;
                            font-size: 11px;
                            line-height: 16px;
                        }

                        span.role {
                            font-family: $poppins;
                            font-style: normal;
                            font-weight: normal;
                            font-size: 11px;
                            line-height: 16px;
                            color: #828282;
                        }
                    }
                }
            }
        }

        .bullets {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 7px;
            margin-top: 5.25rem;

            .bullet {
                width: 10px;
                height: 10px;
                background: $purple;
                border-radius: 10px;
                cursor: pointer;

                &.active {
                    margin-right: 6px;
                    width: 78px;
                    cursor: default;
                }
            }
        }
    }
</style>