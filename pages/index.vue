<template>
    <div>
        <Hero />
        <Portofolio />
        <Specialist />
        <Team />
    </div>
</template>

<script>
import Hero from '~/components/pages/index/Hero';
import Portofolio from '~/components/pages/index/Portofolio';
import Specialist from '~/components/pages/index/Specialist';
import Team from '~/components/pages/index/Team';

export default {
    components: {
        Hero, Portofolio, Specialist, Team
    }    
}
</script>