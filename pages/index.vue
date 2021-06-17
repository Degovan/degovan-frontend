<template>
    <div>
        <Hero />
        <Portofolio :portofolios="portofolios" :categories="categories" />
        <Specialist />
        <Team :teams="teams" />
        <Testimonial :testimonials="testimonials" />
    </div>
</template>

<script>
import Hero from '~/components/pages/index/Hero';
import Portofolio from '~/components/pages/index/Portofolio';
import Specialist from '~/components/pages/index/Specialist';
import Team from '~/components/pages/index/Team';
import Testimonial from '~/components/pages/index/Testimonial';

export default {
    async asyncData({ $axios }) {
        const portofolios = await $axios.get('http://api.degovan.com/api/portofolio');
        const teams = await $axios.get('http://api.degovan.com/api/member');
        const testimonials = await $axios.get('http://api.degovan.com/api/testimonial');
        const categories = await $axios.get('http://api.degovan.com/api/category');

        return { 
            portofolios: portofolios.data.portofolios,
            teams: teams.data.members,
            testimonials: testimonials.data.testimonials,
            categories: categories.data
        }
    },
    components: {
        Hero, Portofolio, Specialist, Team, Testimonial
    }    
}
</script>