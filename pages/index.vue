<template>
    <div>
        <Hero />
        <Portofolio />
        <Specialist />
        <Team />
        <Testimonial />
    </div>
</template>

<script>
import Hero from '~/components/pages/index/Hero';
import Portofolio from '~/components/pages/index/Portofolio';
import Specialist from '~/components/pages/index/Specialist';
import Team from '~/components/pages/index/Team';
import Testimonial from '~/components/pages/index/Testimonial';

export default {
    components: {
        Hero, Portofolio, Specialist, Team, Testimonial
    }    
}
</script>