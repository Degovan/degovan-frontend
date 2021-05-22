<template>
    <section class="testimonial">
        <h1 class="title">Dengarkan apa kata client kami</h1>
        <div class="testimonials">
            <div class="card" v-for="i in 2" :key="i">
                <p class="testimonial-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sit a est enim luctus adipiscing vel ullamcorper elementum pharetra. Metus, aliquam pulvinar lectus neque eu elit. Quisque sagittis est gravida eget molestie consectetur donec purus, lobortis. Scelerisque lacus, quis orci blandit risus.</p>
                <div class="user">
                    <img src="/examples/user-testimonial.png" alt="" class="profile">
                    <div class="detail">
                        <h4 class="name">Haven Gerrad</h4>
                        <span class="role">Ceo as  Coca Cola</span>
                    </div>
                </div>
            </div>
        </div>
        <div class="bullets">
            <span class="bullet active"></span>
            <span class="bullet"></span>
            <span class="bullet"></span>
            <span class="bullet"></span>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    section.testimonial {
        background: #F3F2FD;
        padding: 4.125rem 15.625rem 6.5rem;

        h1.title {
            font-family: $poppins;
            font-weight: 600;
            line-height: 45px;
            text-align: center;
            font-size: 2.25rem;
        }

        .testimonials {
            display: flex;
            gap: 1rem;
            margin-top: 2.625rem;

            .card {
                border-radius: 10px;
                box-shadow: 0px 100px 80px rgba(94, 84, 251, .07), 0px 41.78px 33.4px rgba(94, 84, 251, .0503), 0px 22.34px 17.87px rgba(94, 84, 251, .0417), 0px 12.52px 10.02px rgba(94, 84, 251, .035), 0px 6.65px 5.32px rgba(94, 84, 251, .0283), 0px 2.77px 2.21px rgba(94, 84, 251, .0197);
                padding: 40px;
                background: #FFFFFF;

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

                &.active {
                    margin-right: 6px;
                    width: 78px;
                }
            }
        }
    }
</style>