<template>
    <div>
        <Hero />
        <Portofolio :portofolios="portofolios" />
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
        const portofolios = await $axios.get('/data/portofolios.json');
        const teams = await $axios.get('/data/teams.json');
        const testimonials = await $axios.get('/data/testimonials.json');

        return { 
            portofolios: portofolios.data.data,
            teams: teams.data.data,
            testimonials: testimonials.data.data
        }
    },
    components: {
        Hero, Portofolio, Specialist, Team, Testimonial
    }    
}
</script>