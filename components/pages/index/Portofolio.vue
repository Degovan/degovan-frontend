<template>
    <section class="portofolio">
        <div class="head">
            <h2 class="title">Portofolio</h2>
            <ul class="tabs">
                <li :class="selectedType == category.id ? 'active' : ''" v-for="category in categories" :key="category.id" @click="setSelectedType(category.id)">{{ category.name }}</li>
            </ul>
        </div>
        <div class="portofolios">
            <div class="card" v-for="portofolio in getPortofolioByType" :key="portofolio.id">
                <img :src="portofolio.images_url" alt="">
            </div>
        </div>
    </section>
</template>

<script>
export default {
    props: {
        portofolios: {
            type: Array,
            required: true,
        },
        categories: {
            type: Array,
            required: true,
        }
    },
    data() {
        return {
            selectedType: this.categories ? this.categories[0].id : '',
        }
    },
    computed: {
        getPortofolioByType() {
            let data = this.portofolios.filter((e) => {
                console.log(e);
                console.log(this.selectedType);
                return e.category_id == this.selectedType;
            });
            return data;
        }
    },
    methods: {
        setSelectedType(type) {
            this.selectedType = type;
        }
    }
}
</script>

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

                @include for-size('xs') {
                    font-size: 1.9rem;
                }
            }

            ul.tabs {
                display: flex;
                align-items: center;
                gap: 2rem;
                list-style: none;

                @include for-size('md') {
                    margin-top: 1.15rem;
                }

                @include for-size('sm') {
                    margin-top: 2rem;
                }

                @include for-size('xs') {
                    margin-top: 1.5rem;
                }

                li {
                    color: #828282;
                    font-size: 1.125rem;
                    font-weight: 400;
                    text-align: center;
                    cursor: pointer;
                    transition: all 350ms ease;

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
            margin-top: 50px;

            @include for-size('lg') {
                margin-top: 40px;
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }

            @include for-size('sm') {
                grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
                margin-top: 37.5px;
            }

            .card {
                overflow: hidden;
                border-radius: 10px;
                cursor: pointer;
                transition: all 200ms ease;

                img {
                    width: 100%;
                    height: 283px;
                    transition: all 400ms ease;
                    object-fit: cover;
                    object-position: center;

                    &:hover {
                        transform: scale(1.1);
                    }
                }
            }
        }
    }
</style>